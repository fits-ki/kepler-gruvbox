# Gruvbox for Kepler

Warm, retro dark and light themes in the three classic Gruvbox contrasts. Medium is the familiar default. Hard and soft change the primary background only, the way the original palette does.

This folder matches the layout in [gitkraken/kepler-themes](https://github.com/gitkraken/kepler-themes) `CONTRIBUTING.md`, so it can be copied into a fork later. **Do not open or push a pull request to that repository until Tobias confirms.** The gallery does not allow a theme to take another project's name without that project's okay, and the maintainer login below is a placeholder.

## Variants

| Id | Name | Background |
| --- | --- | --- |
| `gruvbox-dark-hard` | Gruvbox Dark Hard | `#1d2021` |
| `gruvbox-dark-medium` | Gruvbox Dark Medium | `#282828` |
| `gruvbox-dark-soft` | Gruvbox Dark Soft | `#32302f` |
| `gruvbox-light-hard` | Gruvbox Light Hard | `#f9f5d7` |
| `gruvbox-light-medium` | Gruvbox Light Medium | `#fbf1c7` |
| `gruvbox-light-soft` | Gruvbox Light Soft | `#f2e5bc` |

Within dark, and again within light, syntax colors stay the same. Only the surface ladder and the terminal background move.

## Credit

Palette and the original theme by [morhetz](https://github.com/morhetz). Gruvbox is MIT licensed.

- https://github.com/morhetz/gruvbox
- https://gruvbox.org

The family file is also MIT. See `LICENSE`.

## Install

Copy `themes/gruvbox/gruvbox.json` into Kepler's themes folder. Steps, the `gallery.json` distinction, and the upstream warning are in [INSTALL.md](INSTALL.md).

## Contrast

Kepler checks text at 4.5:1. A few official Gruvbox accents miss that floor on these backgrounds, so those roles use the nearest step that passes. Everything else is an official hex from the palette.

Dark roles, judged on `#3c3836`:

- Red `#fb4934` is `#ff836e` (keywords, errors, bright terminal red).
- Blue `#83a598` is `#87aa9c`. Purple `#d3869b` is `#d98ca1`.
- Brand is `#ffb45a` rather than `#fe8019`, so the orange still reads on its own tint. Hover is `#fabd2f`. Pressed is `#fe8019`.
- Comments are `#bdae93`, italic. Gray `#928374` is 3.16:1 here.
- The AI accent is `#d5c4a1`. Aqua `#8ec07c` does not clear the tint check.

Light roles, judged on `#f2e5bc`:

- Green `#79740e` is `#6f6900`. Yellow `#b57614` is `#8c5800`. Aqua `#427b58` is `#397250`.
- Brand `#af3a03` is `#a03200`. Hover is faded red `#9d0006`.
- Comments are `#665c54`, italic.
- The AI accent is `#2b6443`.

Terminal colors follow the classic Gruvbox slots. On a light theme, ANSI black is `#282828` instead of the cream background: Kepler requires slot 0 to contrast, and exempts slots 7 and 15. Slot 7 carries the variant background. Dim terminal colors are the neutral ramp, lifted or deepened only until they clear 4.5:1.

## Upstream pull request

Prepared structurally, not submitted.

1. Replace `TobiasFeigel` in `themes/gruvbox/gallery.json` with the real GitHub login.
2. Get an okay from the Gruvbox maintainers for the name, or choose another display name. `CONTRIBUTING.md` calls this out for ports of projects that keep their own official themes. Ids should stay as they are once anyone has the file installed.
3. Fork `gitkraken/kepler-themes`, copy `themes/gruvbox/` in unchanged, and run `node scripts/check.mjs` with Node 24.2 or later.
4. Open the pull request only after the two points above are settled.

Checked locally against the gallery's `scripts/check.mjs` and Kepler's theme validator: layout, formatting, ids, tags, and contrast all pass. Nothing was pushed to `gitkraken/kepler-themes`.
