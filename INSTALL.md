# Install the Gruvbox themes in Kepler

Kepler reads theme families from your own themes folder. One file holds all six variants. `gallery.json` is listing data for the public gallery. Local use needs `themes/gruvbox/gruvbox.json` only.

## Where Kepler keeps your themes

In Kepler, open **Settings → Appearance**. Under **Your themes**, **Open themes folder** opens the directory. That path is `~/.kepler/themes`. On Windows it is `%USERPROFILE%\.kepler\themes`.

Create the folder if it is not there yet. Kepler reads up to 64 `.json` or `.jsonc` files from it and reloads a file when you save it.

## Load all six variants

1. Copy `themes/gruvbox/gruvbox.json` into the themes folder. Keep the name `gruvbox.json`, or use any other `.json` name. Do not wrap it in an extra folder unless you want to. Kepler loads the file, not the gallery directory.
2. Return to **Settings → Appearance**. The six themes show up under **Your themes**:
   - Gruvbox Dark Hard, Gruvbox Dark Medium, Gruvbox Dark Soft
   - Gruvbox Light Hard, Gruvbox Light Medium, Gruvbox Light Soft
3. Choose how they apply:
   - **System** follows the OS. Each tile has a moon and a sun. The moon is the dark theme, the sun is the light theme. Click the tile itself to use that family for both.
   - **Dark** or **Light** locks the appearance. Click a tile to use it.
4. Medium is the usual Gruvbox background (`#282828` dark, `#fbf1c7` light). Hard is the deeper or brighter background. Soft is the flatter one. Syntax colors do not change between those three.

If a tile says **Has problems** or **Has warnings**, open the badge. A contrast or JSON error names the setting, for example `themes.1.extends`. Saving the file applies the fix. Kepler still loads the other themes in the file when one of them has an error.

## What `gallery.json` is for

`themes/gruvbox/gallery.json` lists maintainers and tags for the gallery index. Kepler does not need it on your machine. Leave it in this repo so the gallery pull request has it.

Maintainer is Tobias Feigel. `maintainers` is `["Mr56k"]`, his GitHub login.

## Contributing it to the gallery

An upstream pull request to the Kepler gallery is intended and in progress. The gallery source is https://github.com/gitkraken/kepler-themes. Its checks are in `CONTRIBUTING.md`. Copy `themes/gruvbox/` into a fork of that repository.

1. Fork the repository and branch from `main`.
2. Copy this repo's `themes/gruvbox/` folder in as `themes/gruvbox/`. The folder must contain only `gruvbox.json` and `gallery.json`.
3. `gallery.json` already lists maintainer `Mr56k` (Tobias Feigel).
4. From the fork, with Node 24.2 or later:

   ```
   node scripts/check.mjs
   ```

   `node scripts/check.mjs --fix` rewrites formatting. The family file has to be plain JSON, two-space indent, trailing newline, and at most 64 KB.
5. Open the pull request against `gitkraken/kepler-themes`. The gallery team reviews every one.

Theme ids (`gruvbox-dark-medium` and the rest) should stay as they are once anyone is using them, because Kepler stores the id of the theme you picked.

This package was checked against that repository's `scripts/check.mjs` and the bundled Kepler validator.
