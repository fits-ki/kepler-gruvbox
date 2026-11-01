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

`themes/gruvbox/gallery.json` lists maintainers and tags for the gallery index. Kepler does not need it on your machine. Leave it in this repo so a later gallery pull request has it.

`maintainers` is currently `["TobiasFeigel"]`. That is a placeholder, not a confirmed GitHub login. Replace it with the real login before any upstream pull request.

## Contributing it to the gallery later

Do not open that pull request until the naming question below is settled.

The gallery source is https://github.com/gitkraken/kepler-themes. Its checks are in `CONTRIBUTING.md`.

1. Fork the repository and branch from `main`.
2. Copy this repo's `themes/gruvbox/` folder in as `themes/gruvbox/`. The folder must contain only `gruvbox.json` and `gallery.json`.
3. Put the real GitHub login in `gallery.json`.
4. From the fork, with Node 24.2 or later:

   ```
   node scripts/check.mjs
   ```

   `node scripts/check.mjs --fix` rewrites formatting. The family file has to be plain JSON, two-space indent, trailing newline, and at most 64 KB.
5. Open a pull request. The gallery team reviews every one.

**Name.** `CONTRIBUTING.md` says not to name a theme after another project without that project's okay. Gruvbox is morhetz's theme (https://github.com/morhetz/gruvbox). Before an upstream pull request, either get the Gruvbox maintainers' okay for the name "Gruvbox", or ship a different display name. Theme ids (`gruvbox-dark-medium` and the rest) should not change after anyone is using them, because Kepler stores the id of the theme you picked.

This package was checked against that repository's `scripts/check.mjs` and the bundled Kepler validator. No pull request was opened and nothing was pushed there.
