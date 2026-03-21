# Bolboreta Keyboard Cheatsheet

> splitkb Aurora Sofle | nice!nano v2 | nice!view | 9 layers

## How to read this

- **Hold** = hold the key down | **Tap** = press and release
- **2xTap** = double-tap (tap-dance) | **Combo** = press two keys simultaneously
- Layers are activated by holding thumb keys or toggling from the ACTIONS layer
- `---` = transparent (falls through to the layer below)

---

## Layer 0: BASE (QWERTY)

> Your daily driver. Homerow mods on both sides, mod-taps on the bottom row.

### Homerow mods (hold a key to get the modifier)

| Left hand | Modifier | | Right hand | Modifier |
|-----------|----------|-|------------|----------|
| Hold A | Shift | | Hold J | Cmd |
| Hold S | Ctrl | | Hold K | Alt |
| Hold D | Alt | | Hold L | Ctrl |
| Hold F | Cmd | | Hold ; | Shift |

**Tip:** Homerow mods use urob's "timeless" method — they only activate if the *next* key is on the **opposite hand**. This prevents misfires when rolling keys like `as` or `df`.

### Bottom row mod-taps (hold = shortcut, tap = letter)

| Key | Tap | Hold |
|-----|-----|------|
| Z | z | Cmd+Z (undo) |
| X | x | Cmd+X (cut) |
| C | c | Cmd+C (copy) |
| V | v | Cmd+V (paste) |

**Tip:** These use `tap-preferred` flavor with 300ms tapping-term. If you're typing fast, the letter always wins. Hold deliberately for the shortcut.

### Thumb cluster (left to right)

| Left thumb | | | | | | Right thumb | | | | |
|---|---|---|---|---|---|---|---|---|---|---|
| Hyper+E | WINDOWS | TMUX/Ctrl+A | Backspace | ACTIONS/Space | | SYMBOLS/Enter | Tab | Up | Cmd+Alt+I | Zoom toggle |

- **TMUX key**: hold for TMUX layer, tap to send the tmux prefix (Ctrl+A)
- **ACTIONS/Space**: hold for ACTIONS layer, tap for Space
- **SYMBOLS/Enter**: hold for SYMBOLS layer, tap for Enter

### Combos (press both keys simultaneously on BASE layer)

| Keys | Result | Mnemonic |
|------|--------|----------|
| F + J | Caps Word | Inner index fingers |
| J + K | Escape | Right homerow adjacent |
| K + L | Tab | Right homerow adjacent |
| L + ; | Enter | Right homerow adjacent |
| , + . | Key Repeat | Bottom row adjacent |
| Z + X | Redo (Cmd+Shift+Z) | Next to undo (hold-Z) |
| U + I | Ctrl+U (vim scroll up) | "Up" area of keyboard |
| M + , | Ctrl+D (vim scroll down) | "Down" area of keyboard |

### Encoders

| Encoder | Action |
|---------|--------|
| Left rotate | Volume up/down |
| Left press | Mute |
| Right rotate | Page up/down |
| Right press | Lock screen (1x) / Sleep (2x) |

### Special keys

| Position | Key |
|----------|-----|
| Far left homerow | Hold: Cmd+Shift+C / Tap: Cmd+Space (Spotlight) |
| Far left bottom | Left arrow |
| Far right bottom | Right arrow |

---

## Layer 1: SYMBOLS

> Activated by holding the right inner thumb key (SYMBOLS/Enter).
> Programming symbols arranged for ergonomic access.

```
         Left                              Right
Top:     `    <    >    -    |              ^    {    }    $
Home:    !    *    /    =    &              #    (    )    ;    "
Bottom:  ~    +    [    ]    %              @    :    ,    .    '
```

**Tip:** Brackets are grouped: `[]` on the left bottom, `{}` on the right top, `()` on the right home. Operators are on the left home row.

### Encoders (SYMBOLS layer)

| Encoder | Action |
|---------|--------|
| Left rotate | RGB saturation |
| Right rotate | RGB hue |

---

## Layer 2: ACTIONS

> Activated by holding the left inner thumb key (ACTIONS/Space).
> Navigation, system controls, Bluetooth, RGB, and media.

### Right side — Navigation & Media

```
         Navigation                      Extras
Top:     PgUp   Home    Up     End       Play/Pause   Screenshot options
Home:    PgDn   Left    Down   Right     Opt+Del      Sleep
Bottom:  RGB+   Scr3    Scr4   Opt+Bksp  ---          Lock
```

| Key | What it does |
|-----|-------------|
| Scr3 | Full screenshot (Cmd+Shift+3) |
| Scr4 | Selection screenshot (Cmd+Shift+4) |
| Screenshot options | Cmd+Shift+5 |
| Opt+Bksp | Delete word left |
| Opt+Del | Delete word right |
| Sleep | Lock screen then system sleep |
| Lock | Lock screen (Ctrl+Cmd+Q) |

### Left side — System

```
Top:     BT_CLR(2x)  BT1  BT2  BT3  BT4  BT5
Middle:  Quit  Close  Menu  USB  BLE
Home:    Shift  Ctrl  Alt  Cmd  CapsLock
Bottom:  Boot(2x)  Undo  Cut  Copy  Paste  RGB-
```

**Safety:** BT_CLR and Bootloader require **double-tap** to activate (single tap does nothing).

### Layer toggles (right number row)

| Key | Toggle |
|-----|--------|
| ExtPwr | External power on/off |
| Win | Toggle WINDOWS layer |
| Mouse | Toggle MOUSE layer |
| Numpad | Toggle NUMPAD layer |
| C_Prev | Previous track |
| C_Next | Next track |

### Encoders (ACTIONS layer)

| Encoder | Action |
|---------|--------|
| Left rotate | RGB brightness |
| Right rotate | RGB saturation |

---

## Layer 3: TMUX

> Activated by holding the TMUX thumb key (left middle thumb).
> All macros send `Ctrl+A` prefix + command automatically.

### Layout concept

- **Left homerow:** session management (save, restore, copy, focus, paste)
- **Right homerow:** navigation (prev/next tab, jump, sessions)
- **Right top:** pane/window creation (split, new tab, rename)
- **Right bottom:** session creation, pane management, fzf
- **Thumbs:** quick-switch (last window, last session)

```
         Left                              Right
Top:     ---  ---  extrakto  ---  ---      ---  |split  -split  new_tab  rename
Home:    save  restore  copy_mode  focus  paste    prev  jump  sessions  next  kill
Bottom:  ---  ---  lazygit  ---  ---       ---  new_sess  break  fzf  ---
Thumb:                                     ---  ---  last_win  last_sess
```

### Quick reference

| Key | tmux command | What it does |
|-----|-------------|-------------|
| save | Ctrl+S | Resurrect: save session |
| restore | Ctrl+R | Resurrect: restore session |
| copy_mode | [ | Enter scroll/copy mode |
| focus | z | Zoom/focus current pane |
| paste | P | Paste from tmux buffer |
| extrakto | Tab | Fuzzy find text in pane |
| lazygit | g | Open lazygit in new window |
| \|split | \| | Split pane vertically |
| -split | - | Split pane horizontally |
| new_tab | c | New window |
| rename | , | Rename window |
| prev/next | p/n | Previous/next window |
| jump | j | tmux-jump: jump to character |
| sessions | s | sesh: session picker (fzf) |
| kill | x | Kill current pane |
| new_sess | S | New session |
| break | b | Break pane into own window |
| fzf | F | tmux-fzf |
| last_win | Ctrl+A | Toggle last window |
| last_sess | L | Toggle last session (sesh) |

---

## Layer 4: FUN (Conditional)

> Automatically activated when **SYMBOLS + ACTIONS** are both held.
> No need to press a dedicated key — just hold both thumb keys.

```
         Left                    Right
Top:     ---  ---  ---  ---      F10  F11  F12
Home:    Shift  Ctrl  Alt  Cmd   F4   F5   F6
Bottom:  ---  ---  ---  ---      F1   F2   F3
```

**Tip:** F-keys are in numpad-style layout (1-3 bottom, 4-6 middle, 7-9 top, 10-12 on the top row). Left side has mods for combos like Shift+F5.

---

## Layer 5: ZOOM

> Toggled from BASE layer (right outermost thumb key). Press `to BASE` to exit.
> Shortcuts for Zoom meetings.

| Key position | Shortcut | Action |
|--|--|--|
| Left encoder press | Mute (K_MUTE) | Toggle microphone |
| Right encoder press | Cmd+Shift+A | Toggle audio |
| Left thumb 1 | Cmd+Shift+S | Screen share |
| Left thumb 2 | Cmd+Shift+R | Start/stop recording |
| Right thumb 3 | Cmd+Shift+V | Toggle video |
| Right thumb 4 | to BASE | Exit ZOOM layer |

---

## Layer 6: WINDOWS (yabai/skhd)

> Activated by holding the WINDOWS thumb key (left thumb 2).
> Controls yabai tiling window manager via skhd shortcuts.

### Layout concept: spatial metaphor

- **Home row right = FOCUS** (Alt+HJKL) — move focus between windows
- **Top row right = SWAP** (Shift+Alt+HJKL) — swap window positions
- **Number row = MOVE TO SPACE** — send window to space 1-7
- **Left hand = LAYOUT** commands — mirror, rotate, zoom, balance
- **Thumbs = LAYOUT MODE** — stack vs BSP vs float

```
         Left                                    Right
Number:  Spc1  Spc2  Spc3  Spc4  Spc5           Spc6  Spc7  ---  ---  PrevSpc  NextSpc
Top:     ---  ---  ---  ---  ---                 SwapW  SwapS  SwapN  SwapE  DispN  MvDispN
Home:    ---  Desk  Zoom  ---  ---               FocW   FocS   FocN   FocE   ---  ---
Bottom:  ---  MirX  MirY  Rotate  ---            ---  DispS  Balance  Float  MvDispS  ---
Thumb:   ---  ---  ---  Stack                    BSP  Flt+Grid  ---  ---
```

### Quick reference

| Key | skhd shortcut | What it does |
|-----|-------------|-------------|
| FocH/J/K/L | Alt+H/J/K/L | Focus window west/south/north/east |
| SwapH/J/K/L | Shift+Alt+H/J/K/L | Swap window in direction |
| Spc1-7 | Shift+Alt+1-7 | Move window to space # |
| PrevSpc | Shift+Alt+P | Move window to previous space |
| NextSpc | Shift+Alt+N | Move window to next space |
| DispN | Alt+I | Focus display north |
| DispS | Alt+M | Focus display south |
| MvDispN | Shift+Alt+I | Move window to display north |
| MvDispS | Shift+Alt+M | Move window to display south |
| Desk | Alt+D | Toggle show desktop |
| Zoom | Shift+Alt+Z | Toggle fullscreen zoom |
| MirX | Shift+Alt+X | Mirror x-axis |
| MirY | Shift+Alt+Y | Mirror y-axis |
| Rotate | Shift+Alt+R | Rotate layout 270° |
| Balance | Shift+Alt+E | Balance window sizes |
| Float | Shift+Alt+T | Toggle float |
| Stack | Alt+S | Stack layout |
| BSP | Alt+B | BSP layout |
| Flt+Grid | Shift+Alt+Space | Float + center grid |

---

## Layer 7: MOUSE

> Toggled from ACTIONS layer. Press `to BASE` (left inner thumb) to exit.

```
         Left (scroll)                   Right (move)
Top:     ---  ---  ---  ---              ---  ---  Move Up  ---
Home:    ---  Scrl Left  Scrl Up  Scrl Down  Scrl Right    ---  Move Left  Move Down  Move Right
Bottom:  ---  ---  ---  ---              ---  ---  ---  ---
Thumb:   ---  ---  ---  to BASE          LClick  RClick  MClick  ---
```

**Tip:** Left hand controls scroll (WASD-style on homerow), right hand controls cursor movement. Clicks are on the right thumb cluster.

---

## Layer 8: NUMPAD

> Toggled from ACTIONS layer. Press `tog NUMPAD` (right thumb 4) to exit.

```
         Left (navigation)               Right (numpad)
Number:  ---  ---  ---  ---  ---         ---  /  *  -  ---
Top:     PgUp  Home  Up   End  ---       ---  7  8  9  +
Home:    PgDn  Left  Down Right ---      ---  4  5  6  =
Bottom:  Shift  Ctrl  Alt  Cmd  ---      ---  1  2  3  Enter
Thumb:   ---  ---  ---  ---              Enter  0  0  .  tog NUMPAD
```

**Tip:** Left hand has full navigation (arrows + page/home/end) so you can navigate while entering numbers. Bottom-left has sticky mods (one-shot) — tap Shift then tap a number key for shifted input.

---

## Encoders summary by layer

| Layer | Left encoder | Right encoder |
|-------|-------------|---------------|
| BASE | Volume | Page Up/Down |
| SYMBOLS | (inherit from BASE) | (inherit from BASE) |
| ACTIONS | Volume | Ctrl+U/Ctrl+D (vim scroll) |
| ZOOM | Volume | Page Up/Down |
| MOUSE | Page Up/Down | Page Up/Down |
| Others | (inherit from below) | (inherit from below) |

> **Note:** RGB underglow is disabled for battery savings (~15-29mA saved). To re-enable, uncomment the RGB config in `splitkb_aurora_sofle.conf` and restore the commented-out RGB lines in the keymap.

## Safety features

| Feature | Protection |
|---------|-----------|
| BT_CLR | Double-tap required (single tap = nothing) |
| Bootloader | Double-tap required (single tap = nothing) |
| Lock Screen | Macro with explicit press/release of Ctrl+Cmd |
| Sleep | Locks screen first, then sends C_SLEEP after 200ms |
