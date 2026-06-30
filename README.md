# Corne Keymap

Personal Corne keymap. Mac. vim, tmux, aerospace, py/rust. Colemak-DH alphas. ZMK Studio enabled (left side).

This README documents the **current** layout. It is versioned alongside `config/corne.keymap` — each layout iteration updates both.

## Conventions

- `ESC/⌃` — mod-tap: tap = ESC, hold = ⌃
- `SK ⌃ ⌘ ⌥ ⇧` — sticky mod (tap = oneshot, hold = held mod)
- `SL 1` `SL 2` `SL 3` — sticky layer (tap = next-key on layer, hold = momentary)
- `▽` — transparent (falls through to base)
- `CAPW` — caps_word
- `SCRN` — `⌘+⇧+4` (mac screenshot)

---

## L0 — Base

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ TAB │  Q  │  W  │  F  │  P  │  B  │    │  J  │  L  │  U  │  Y  │  ;  │ DEL │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│ESC/⌃│  A  │  R  │  S  │  T  │  G  │    │  M  │  N  │  E  │  I  │  O  │  '  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│SK ⌥ │  Z  │  X  │  C  │  D  │  V  │    │  K  │  H  │  ,  │  .  │  /  │SK ⌘ │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ENT │ SPC │SL 1 │    │SL 2 │BSPC │SK ⇧ │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

Thumbs L→R: `ENT` · `SPC` · `SL 1` ‖ `SL 2` · `BSPC` · `SK ⇧`

---

## L1 — Num + Nav (tap `SL 1` sticky, or hold)

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│SL 3 │  ▽  │HOME │ ↑   │ END │PGUP │    │  /  │  7  │  8  │  9  │  *  │  -  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ▽  │ ←   │ ↓   │ →   │PGDN │    │  .  │  4  │  5  │  6  │  +  │  =  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │SK ⇧ │SK ⌘ │  ▽  │CAPW │SCRN │    │  0  │  1  │  2  │  3  │  ▽  │ ENT │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ▽   │ ▽   │ ▽   │    │ ▽   │ ▽   │ ▽   │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

- `Z bot` = `SK ⇧`, `X bot` = `SK ⌘` — mouse-chord mods (right hand on mouse, tap SL 1 → tap mod → click)
- `SL 3` top-left = sole access path to L3 (tap SL 1 → tap SL 3 → tap target, layer auto-clears)

---

## L2 — Sym (tap `SL 2` sticky, or hold)

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│  ▽  │  !  │  @  │  #  │  $  │  %  │    │  ^  │  &  │  *  │  =  │  |  │  `  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  \  │  {  │  [  │  (  │  +  │    │  <  │  ?  │  _  │  :  │  ;  │  '  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ~  │  }  │  ]  │  )  │  -  │    │  >  │  "  │  ,  │  .  │  /  │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ▽   │ ▽   │ ▽   │    │ ▽   │ ▽   │ ▽   │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

---

## L3 — Adjust (via L1 → `SL 3`)

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ F1  │ F2  │ F3  │ F4  │ F5  │ F6  │    │ F7  │ F8  │ F9  │ F10 │ F11 │ F12 │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│BTCLR│ BT0 │ BT1 │ BT2 │ BT3 │ BT4 │    │MUTE │VOL- │VOL+ │PREV │PLAY │NEXT │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│RESET│BOOT │  ▽  │  ▽  │  ▽  │  ▽  │    │  ▽  │  ▽  │  ▽  │  ▽  │BOOT │RESET│
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ▽   │ ▽   │ ▽   │    │ ▽   │ ▽   │ ▽   │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

---

## Notes

- **Aerospace**: hold `SK ⌥` (left pinky) + mash hjkl on right hand → cross-hand chord
- **Tmux prefix** `⌃+SPC`: hold `ESC/⌃` (left outer mid) → tap SPACE
- **Sticky stacking**: tap `SK ⌘`, tap `SK ⇧`, tap letter → ⌘+⇧+letter
- **Hold sticky for repeat**: holding the sticky key = acts as held mod

## Build / flash

- Docker: `zmkfirmware/zmk-build-arm:stable`. West workspace already at repo root (`.west/` + `zmk/` + `zephyr/` + `modules/` cloned).
- Build: `docker run --rm -v $PWD:/workspace -w /workspace zmkfirmware/zmk-build-arm:stable bash -c 'west build -d build/left ...'`
- Outputs to `firmware/*.uf2`
- Flash: double-tap reset on half → `NICENANO` mounts → `cp firmware/corne_<side>.uf2 /Volumes/NICENANO/`
- ZMK Studio enabled on left (snippet `studio-rpc-usb-uart`) — direct flash works for keymap updates, no settings_reset needed

## Open concerns

- TAB / ESC on left outer column = pinky reach
- `SK ⌘` on right outer bot pinky = sustained cmd-hold awkward
- DEL on top-right outer pinky corner
- `ESC/⌃` mod-tap: tune flavor (`tap-preferred` default), watch for misfires on vim `<C-…>` chords
