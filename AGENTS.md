# Agent Guide

Personal ZMK keymap for wireless Corne (nice_nano_v2 + nice_view). Mac user, Colemak-DH, vim, tmux, aerospace, py/rust.

## Source of truth

- **`README.md`** — layout is versioned here. Read this to understand current keymap. Update alongside `config/corne.keymap` for every change.
- **`config/corne.keymap`** — the actual ZMK devicetree. Layers, behaviors, macros defined here.
- **`config/west.yml`** — west manifest (pins ZMK to `v0.3`).
- **`build.yaml`** — CI build matrix (shows the exact shield strings used).

Ignore `docs/` — it was nuked. Don't recreate.

## Workflow

1. Discuss layout changes with user in chat (they iterate).
2. Update `README.md` layout tables + notes.
3. Update `config/corne.keymap` to match.
4. Build via Docker (see below).
5. User plugs left half, double-taps reset → NICENANO mount → cp uf2.
6. Commit + push when user asks.

## Build

Docker with west workspace at repo root (`.west/`, `zmk/`, `zephyr/`, `modules/` already cloned).

Full build (both halves):
```bash
docker run --rm -v "$PWD":/workspace -w /workspace zmkfirmware/zmk-build-arm:stable bash -c '
  west zephyr-export > /dev/null 2>&1 &&
  west build -d build/left  -s zmk/app -b nice_nano_v2 -S studio-rpc-usb-uart -- -DSHIELD="corne_left nice_view_adapter nice_view"  -DZMK_CONFIG=/workspace/config &&
  west build -d build/right -s zmk/app -b nice_nano_v2                          -- -DSHIELD="corne_right nice_view_adapter nice_view" -DZMK_CONFIG=/workspace/config &&
  cp build/left/zephyr/zmk.uf2  firmware/corne_left.uf2 &&
  cp build/right/zephyr/zmk.uf2 firmware/corne_right.uf2
'
```

Left-only (typical for keymap tweaks):
```bash
docker run --rm -v "$PWD":/workspace -w /workspace zmkfirmware/zmk-build-arm:stable bash -c '
  west zephyr-export > /dev/null 2>&1 &&
  west build -d build/left -s zmk/app -b nice_nano_v2 -S studio-rpc-usb-uart -- -DSHIELD="corne_left nice_view_adapter nice_view" -DZMK_CONFIG=/workspace/config &&
  cp build/left/zephyr/zmk.uf2 firmware/corne_left.uf2
'
```

Notes:
- `west zephyr-export` needed after pristine builds; harmless to include always.
- `-s zmk/app` required when build dir is empty.
- Never build right alone unless ZMK version or shield config changed (see split-keyboard note).

## Flash

Bootloader mounts as `/Volumes/NICENANO`. Copy uf2:
```bash
cp firmware/corne_left.uf2 /Volumes/NICENANO/
```

The `could not copy extended attributes: Device not configured` error is **cosmetic** — file writes before bootloader reboots. Volume then unmounts, keyboard rejoins. Confirm by re-checking `/Volumes/`.

## Split keyboard behavior

**Left = central** (owns keymap, USB, BLE host). **Right = peripheral** (reports raw matrix events to left over BLE).

- Keymap-only changes → flash **left only**.
- Flash right too when: ZMK version upgrade, shield/board config change, first-time pairing, or right's own behaviors change.

## Current layout summary (2026-06-30)

Layers (5 active + 3 reserved for ZMK Studio slots):
- **L0 Base** — Colemak-DH. HRM: GACS (⌘⌥⌃⇧, ⇧ on index). HYPER on G/M as HRM hold.
- **L1 NAV** — arrows on M/N/E/I (vim HJKL feel), clipboard, page nav, media, BT profiles.
- **L2 SYM_L** — left-hand symbols (matches user's previous keymap). Macros `-> => !=` on thumbs.
- **L3 NUM** — numpad + math ops. `-` at bot-inner (mirrors SYM_L). `=` on thumb-outer, `%` on home-pinky.
- **L4 SYM_R** — right-hand symbols (matches user's previous keymap). Macros `<= == >=` on thumbs.

Thumbs (L→R): `LT4 SYM_R` · SPC · `LT1 NAV` ‖ `LT3 NUM` · BSPC · `LT2 SYM_L`
- NAV/NUM on inner (big) thumbs. Sym on outer.
- `LT` = custom hold-tap: tap → sticky-layer (`&sl`), hold → momentary (`&mo`).

Base bot outer: `key_repeat` (left), `caps_word` (right).
Right outer col: `'` top, ENT mid; DEL top-right corner.

HYPER = `LS(LC(LA(LGUI)))` = all 4 mods. User handles mac conflicts via Karabiner/Aerospace.

## Design decisions worth preserving

- **HRM tuning**: `flavor="balanced"`, `tapping-term-ms=200`, `quick-tap-ms=175`, `require-prior-idle-ms=150`, `hold-trigger-key-positions` = opposite-hand only. Prevents same-hand roll misfires.
- **`lt` name collides with ZMK builtin** (which is `&lt` layer-tap). Custom hold-tap is named `lth`.
- **Sticky mods** use custom `skq` (`&sk` with `release-after-ms=1000` and `quick-release`) so holding still acts as held-mod.
- **Outer columns transparent (▽) on layers 1-4** — base TAB/ESC/HYP/DEL/ENT/CAPW always reachable except where a layer explicitly overrides (SYM_R overrides right outer for `'` and `` ` ``).
- **Right side of SYM_L / NUM / SYM_R kept empty** except HRM mirror — user's explicit preference. Don't add letters/syms there.
- **No mouse layer** — user uses trackpad.
- **Split sym layers**: SYM_L and SYM_R mirror the user's previous single-sym-layer left/right halves so muscle memory survived the migration.

## User preferences

- Terse responses, low fluff. Session often runs in caveman mode.
- Uses `uv` for Python (never pip/pipx/poetry). See `~/.claude/projects/-Users-junyongtan-projects-corne-wireless-view-zmk-config/memory/`.
- Confirms flash by saying "plugged in" / "ready to flash" — then run the cp command.
- Commits + pushes on explicit request only.

## Commit style

- One-line subject (imperative, ≤ ~65 chars).
- Body explains **why**, not what (README already documents what).
- Sign off with `Co-Authored-By: Claude Opus 4.7 <noreply@anthropic.com>`.

## Common pitfalls

- Don't invent new `docs/` files — user removed them intentionally.
- Don't stage `modules/`, `zephyr/`, `zmk/`, `firmware/*.uf2`, `firmware/*.log`, `build/` — all `.gitignore`d.
- Don't rebuild both halves for keymap changes; wastes time (~5 min vs 2).
- Don't rename or move `lth` behavior without checking base_layer thumb bindings — they reference it directly.
- Don't reintroduce `lt` as a custom behavior name; conflicts with `zmk,behavior-layer-tap`.
- HYPER in `#define HYPER` currently uses `LS(LC(LA(LGUI)))`. Changing it propagates to G/M HRM automatically.
