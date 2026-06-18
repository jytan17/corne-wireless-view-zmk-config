# WIP Layout — Last Agreed

Personal Corne keymap target. Mac. vim, tmux, aerospace, py/rust. Colemak-DH alphas.

## Conventions

- `SK ⌃ ⌘ ⌥ ⇧` — sticky mod (tap = oneshot, hold = held mod)
- `MO 1` `MO 2` — momentary layer hold
- L3 ADJUST = tri-state (hold `MO 1` + `MO 2`)
- `▽` — transparent (falls through to base)
- `CAPW` — caps_word
- `SCRN` — cmd+shift+4 (mac screenshot)

---

## L0 — Base

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ TAB │  Q  │  W  │  F  │  P  │  B  │    │  J  │  L  │  U  │  Y  │  ;  │ DEL │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│ ESC │  A  │  R  │  S  │  T  │  G  │    │  M  │  N  │  E  │  I  │  O  │ ENT │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│SK ⌥ │  Z  │  X  │  C  │  D  │  V  │    │  K  │  H  │  ,  │  .  │  /  │SK ⇧ │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │SK ⌃ │MO 1 │ SPC │    │BSPC │MO 2 │SK ⌘ │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

---

## L1 — Num + Nav (hold MO 1)

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ TAB │  ▽  │HOME │ ↑   │ END │PGUP │    │  /  │  7  │  8  │  9  │  *  │  -  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│ ESC │  ▽  │ ←   │ ↓   │ →   │PGDN │    │  .  │  4  │  5  │  6  │  +  │  =  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ▽  │  ▽  │  ▽  │CAPW │SCRN │    │  0  │  1  │  2  │  3  │  ,  │ ENT │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ▽   │ ▽   │ ▽   │    │BSPC │ ▽   │ ▽   │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

Free slots (left): `Q top`, `A mid`, `Z bot`, `X bot`, `C bot` — TBD.

---

## L2 — Sym (hold MO 2)

```
┌─────┬─────┬─────┬─────┬─────┬─────┐    ┌─────┬─────┬─────┬─────┬─────┬─────┐
│ TAB │  !  │  @  │  #  │  $  │  %  │    │  ^  │  &  │  *  │  =  │  |  │  `  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│ ESC │  \  │  {  │  [  │  (  │  +  │    │  <  │  ?  │  _  │  :  │  ;  │  '  │
├─────┼─────┼─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┼─────┼─────┤
│  ▽  │  ~  │  }  │  ]  │  )  │  -  │    │  >  │  "  │  ,  │  .  │  /  │  ▽  │
└─────┴─────┴─────┼─────┼─────┼─────┤    ├─────┼─────┼─────┼─────┴─────┴─────┘
                  │ ▽   │ ▽   │ ▽   │    │ ▽   │ ▽   │ ▽   │
                  └─────┴─────┴─────┘    └─────┴─────┴─────┘
```

---

## L3 — Adjust (tri-state: hold MO 1 + MO 2)

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

## Combos

None currently.

## Open Concerns

- `'` (apostrophe) not on base — English contractions need MO 2 chord
- TAB / ESC on left outer column = pinky reach
- SK ⌘ on right outer thumb = sustained cmd-hold awkward
- DEL on top-right outer pinky corner
- MO 1 and SK ⌃ adjacent left thumbs = fat-finger risk
- 5 free L1 slots TBD

## Notes

- **Aerospace**: hold `SK ⌥` (left pinky) + mash hjkl on right hand → cross-hand chord
- **Tmux prefix** `C-Space`: tap `SK ⌃` (left mid thumb) → tap SPACE
- **Sticky stacking**: tap `SK ⌘`, tap `SK ⇧`, tap letter → cmd+shift+letter
- **Hold sticky for repeat**: holding the sticky key = acts as held mod
