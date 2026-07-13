# Corne Keymap

Personal Corne keymap. Mac. vim, tmux, aerospace, py/rust. Colemak-DH alphas. ZMK Studio enabled (left side). Miryoku-inspired: sticky mods, split sym layers, mouse layer.

This README documents the **current** layout. Versioned alongside `config/corne.keymap` — each layout iteration updates both.

## Conventions

- `SK ⌘ ⌥ ⌃ ⇧` — sticky mod (tap = oneshot for next key, hold = held mod)
- `LT N` — layer tap-hold (tap = sticky-layer for next key, hold = momentary layer)
- `HYP` — Hyper (⌘+⌥+⌃+⇧) for app-launcher / window manager
- `CAPW` — caps_word (auto-shift letters until space/punct)
- `SCRN` — `⌘+⇧+4` (mac screenshot / snippet tool)
- `->` `=>` `!=` `<=` `==` `>=` — macros (emit multiple keys)
- `▽` — transparent (falls through to base)
- `·` — none / blank

## Thumb cluster

NAV and NUM on **inner** (big) thumbs. Sym layers on outer thumbs.

| Position    | Tap / Hold        | Notes                            |
|-------------|-------------------|----------------------------------|
| Left-outer  | `LT 4` SYM_R      | Right hand active when held      |
| Left-mid    | `SPC` plain       |                                  |
| Left-inner  | `LT 1` NAV        | Right hand active when held      |
| Right-inner | `LT 3` NUM        | Left hand active when held       |
| Right-mid   | `BSPC` plain      |                                  |
| Right-outer | `LT 2` SYM_L      | Left hand active when held       |

---

## L0 — Base

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ TAB │  Q  │  W  │  F  │  P  │  B  │    │  J  │  L  │  U  │  Y  │  '  │ DEL │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│ ESC │  A  │  R  │  S  │  T  │  G  │    │  M  │  N  │  E  │  I  │  O  │ ENT │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│ HYP │  Z  │  X  │  C  │  D  │  V  │    │  K  │  H  │  ,  │  .  │  /  │CAPW │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │LT 4 │ SPC │LT 1 │    │LT 3 │BSPC │LT 2 │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

Home row is plain alphas — no HRM. Modifiers come from sticky mods on layers.

---

## L1 — NAV (hold left-inner thumb; right hand types)

Arrows on M/N/E/I (vim HJKL feel). Page nav on bottom row. Media on right thumbs. Bluetooth on left bottom row. Left home row = SK mod mirror. `MOU` at G-slot = hold to activate MOUSE layer.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ▽  │ BCL │  ·  │  ·  │  ·  │  ·  │    │ RDO │ PST │ CPY │ CUT │ UND │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │SK ⌘ │SK ⌥ │SK ⌃ │SK ⇧ │ MOU │    │  ←  │  ↓  │  ↑  │  →  │ INS │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │ BT0 │ BT1 │ BT2 │ BT3 │ BT4 │    │HOME │PGDN │PGUP │ END │SCRN │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │  ·  │  ▽  │  ▽  │    │MUTE │VOL- │VOL+ │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

---

## L2 — SYM_L (hold right-outer thumb; left hand types)

Left hand carries symbols (matches previous keymap's left sym half). Right home row = SK mod mirror. Left thumbs host cross-hand-token macros `->` `=>` `!=`.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ▽  │  !  │  @  │  #  │  $  │  %  │    │  ·  │  ·  │  ·  │  ·  │  ·  │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  \  │  {  │  [  │  (  │  +  │    │  ·  │SK ⇧ │SK ⌃ │SK ⌥ │SK ⌘ │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ~  │  }  │  ]  │  )  │  -  │    │  ·  │  ·  │  ·  │  ·  │  ·  │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ->  │ =>  │ !=  │    │  ▽  │  ▽  │  ▽  │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

One-hand operations: `()` `{}` `[]` all left-only.

---

## L3 — NUM (hold right-inner thumb; left hand types)

Numpad + math ops on left. Digits: 1-3 bot, 4-6 home, 7-9 top, 0 on thumb. Ops on index-inner col: `* + -` (matches SYM_L `-` position at bot-inner). `= ` on thumb, `%` on pinky home. Right home row = SK mod mirror.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ▽  │  /  │  7  │  8  │  9  │  *  │    │  ·  │  ·  │  ·  │  ·  │  ·  │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  %  │  4  │  5  │  6  │  +  │    │  ·  │SK ⇧ │SK ⌃ │SK ⌥ │SK ⌘ │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ,  │  1  │  2  │  3  │  -  │    │  ·  │  ·  │  ·  │  ·  │  ·  │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │  .  │  0  │  =  │    │  ▽  │  ▽  │  ▽  │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

`-` at bot-inner mirrors SYM_L position. `[` `]` `;` `` ` `` `\` accessible on SYM_L/SYM_R.

---

## L4 — SYM_R (hold left-outer thumb; right hand types)

Right hand carries symbols (matches previous keymap's right sym half). Left home row = SK mod mirror. Right thumbs host comparison-operator macros `<=` `==` `>=`.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ▽  │  ·  │  ·  │  ·  │  ·  │  ·  │    │  ^  │  &  │  *  │  =  │  |  │  `  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │SK ⌘ │SK ⌥ │SK ⌃ │SK ⇧ │  ·  │    │  <  │  ?  │  _  │  :  │  ;  │  '  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ·  │  ·  │  ·  │  ·  │  ·  │    │  >  │  "  │  ,  │  .  │  /  │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │  ▽  │  ▽  │  ▽  │    │ <=  │ ==  │ >=  │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

One-hand operations: `""` `''` `<>` `::` `||` all right-only.

---

## L5 — MOUSE (hold NAV thumb + G; right hand mouses)

Nested layer, reached only from NAV. Hold left-inner-thumb (NAV) then hold G-slot to activate — release either to exit. Right hand does pointer / scroll / click. Left home row = SK mod mirror for `⌘-click`, `⇧-click`, `⌥-click`, `⌃-click`.

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ▽  │  ·  │  ·  │  ·  │  ·  │  ·  │    │  ·  │  ·  │  ·  │  ·  │  ·  │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │SK ⌘ │SK ⌥ │SK ⌃ │SK ⇧ │  ▽  │    │ M←  │ M↓  │ M↑  │ M→  │  ·  │  ▽  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ·  │  ·  │  ·  │  ·  │  ·  │    │ S←  │ S↓  │ S↑  │ S→  │  ·  │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │  ▽  │  ▽  │  ▽  │    │ LMB │ MMB │ RMB │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

- `M← M↓ M↑ M→` — pointer move (mirrors NAV arrow keys)
- `S← S↓ S↑ S→` — scroll wheel
- `LMB MMB RMB` — left / middle / right click on right thumbs

---

## Two-character token coverage

| Token   | Where                  | How                          |
|---------|------------------------|------------------------------|
| `()`    | SYM_L left             | tap `(` tap `)`              |
| `{}`    | SYM_L left             | tap `{` tap `}`              |
| `[]`    | SYM_L left             | tap `[` tap `]`              |
| `""`    | SYM_R right            | tap `"` twice                |
| `''`    | SYM_R right            | tap `'` twice                |
| `<>`    | SYM_R right            | tap `<` tap `>`              |
| `::`    | SYM_R right            | tap `:` twice                |
| `\|\|`  | SYM_R right            | tap `\|` twice               |
| `&&`    | SYM_R right            | tap `&` twice                |
| `->`    | SYM_L thumb macro      | tap macro                    |
| `=>`    | SYM_L thumb macro      | tap macro                    |
| `!=`    | SYM_L thumb macro      | tap macro                    |
| `<=`    | SYM_R thumb macro      | tap macro                    |
| `==`    | SYM_R thumb macro      | tap macro                    |
| `>=`    | SYM_R thumb macro      | tap macro                    |

---

## Behaviors

### `lt` (layer tap-hold for thumbs)

Custom hold-tap: tap → sticky-layer, hold → momentary-layer.

### `SK` (sticky mods)

ZMK built-in `&sk` with `quick-release` so holding behaves as held-mod.

---

## Build / flash

- Docker: `zmkfirmware/zmk-build-arm:stable`. West workspace at repo root (`.west/` + `zmk/` + `zephyr/` + `modules/` cloned).
- Build both halves (clean):
  ```
  docker run --rm -v "$PWD":/workspace -w /workspace zmkfirmware/zmk-build-arm:stable bash -c '
    west zephyr-export &&
    west build -d build/left  -s zmk/app -b nice_nano_v2 -S studio-rpc-usb-uart -- -DSHIELD="corne_left nice_view_adapter nice_view"  -DZMK_CONFIG=/workspace/config &&
    west build -d build/right -s zmk/app -b nice_nano_v2                          -- -DSHIELD="corne_right nice_view_adapter nice_view" -DZMK_CONFIG=/workspace/config &&
    cp build/left/zephyr/zmk.uf2  firmware/corne_left.uf2 &&
    cp build/right/zephyr/zmk.uf2 firmware/corne_right.uf2
  '
  ```
- The `west zephyr-export` step registers the Zephyr CMake package so `find_package(Zephyr)` resolves; required after pristine builds.
- Incremental rebuilds (after just changing keymap): drop `west zephyr-export` and add `-s zmk/app` to the `west build` invocations only if pristine.
- Flash: double-tap reset on half → `NICENANO` mounts → `cp firmware/corne_<side>.uf2 /Volumes/NICENANO/`
- ZMK Studio enabled on left (snippet `studio-rpc-usb-uart`) — direct flash works for keymap updates, no settings_reset needed

## Open Concerns

- HYP requires Raycast/Hammerspoon/AeroSpace binding to be useful.
- DEL on top-right outer corner = pinky reach. Acceptable since DEL is occasional.
- `` ` `` and `'` on SYM_R right outer cols override base DEL/ENT while SYM_R held. Rarely an issue.
- `,` `.` `/` on SYM_R right-bot duplicate base — harmless redundancy.
- MOUSE layer trigger is same-hand grip (left thumb + left index) — fine for short bursts, tiring for long drags.
