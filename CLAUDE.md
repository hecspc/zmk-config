# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ZMK firmware configuration for a **splitkb Aurora Sofle** split keyboard with nice!view displays, nice_nano controllers, rotary encoders, RGB underglow, and mouse emulation. The keyboard is named "Bolboreta".

## Build & Deploy

Firmware is built entirely via GitHub Actions — there is no local build. Pushing to `main` triggers two workflows:

- **Build firmware** (`.github/workflows/build.yml`): calls ZMK's reusable `build-user-config.yml` workflow. The build matrix is defined in `build.yaml` (left half with ZMK Studio enabled, right half, and settings_reset).
- **Update keymap images** (`.github/workflows/img.yml`): runs `keymap-drawer` via `img/update` script to regenerate `img/splitkb_aurora_sofle.svg` and auto-commits it.

Download firmware `.uf2` files from the GitHub Actions build artifacts. Flash by double-tapping the reset button on the nice_nano to enter bootloader mode, then copy the `.uf2` to the mounted drive.

There is also a GitLab CI mirror pipeline (`.gitlab-ci.yml`) that syncs from GitHub on a schedule.

## Commands

```bash
# Regenerate keymap SVG locally (requires keymap-drawer: pip install keymap-drawer)
./img/update
```

## Architecture

### Keymap structure (`config/splitkb_aurora_sofle.keymap`)

The keymap uses a 60-key matrix (defined in `config/keys/60.h`) with 8 layers:

| # | Layer | Purpose |
|---|-------|---------|
| 0 | BASE | QWERTY with positional homerow mods (urob's timeless method) |
| 1 | SYMBOLS | Programming symbols arranged ergonomically |
| 2 | ACTIONS | Navigation, Bluetooth, RGB, output toggle, bootloader |
| 3 | TMUX | Tmux macros (prefix is Ctrl+A) |
| 4 | FUN | Function keys (F1-F12) — activated as conditional layer when SYMBOLS+ACTIONS held |
| 5 | ZOOM | Zoom meeting shortcuts (toggle layer) |
| 6 | WINDOWS | Window management (Alt-based shortcuts) |
| 7 | MOUSE | Mouse movement and scroll emulation |

### Key position headers (`config/keys/`)

- `60.h` — Defines named positions (LN0-LN5, LT0-LT5, LM0-LM5, etc.) for the 60-key Aurora Sofle matrix. Also sets extra key overrides (`_LTX`, `_LBX`, etc.) for the extended layout.
- `base.h` — Defines `KEYS_L`, `KEYS_R`, `KEYS_T` groups used by homerow mod `hold-trigger-key-positions` to restrict activation to the opposite hand.

### Homerow mods

Two custom hold-tap behaviors (`hml`/`hmr`) implement positional homerow mods: a hold only activates if the next key is on the opposite side of the keyboard. Parameters: 280ms tapping-term, 175ms quick-tap, balanced flavor, `hold-trigger-on-release`.

### Keymap image generation

The `img/update` script runs `keymap-drawer` with `img/config.yaml` (drawing style, key label overrides, emoji mappings) to produce the SVG. The `img/splitkb_aurora_sofle.yaml` is the parsed intermediate representation. When changing the keymap, the SVG is auto-regenerated on push.

## Editing Guidelines

- In the `.keymap` file, `#include "keys/60.h"` and `"keys/base.h"` must appear before the ZMK `#include` directives — `60.h` defines position macros and layout overrides that `base.h` depends on.
- Layer indices (0-7) are `#define`d at the top of the keymap file — always use the named constants.
- The `build.yaml` left half includes cmake args for ZMK Studio, split battery proxying, and smooth scrolling — keep these in sync if changing the build configuration.
- The nice!view CS pin is remapped to D0 via `&nice_view_spi` override in the keymap.
- Tmux macros all use `LC(A)` (Ctrl+A) as the prefix — update all macros if the tmux prefix changes.
