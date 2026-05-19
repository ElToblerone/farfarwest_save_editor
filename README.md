# Far Far West Save Editor

Save editor for [Far Far West](https://store.steampowered.com/app/3124540/_Far_Far_West/), based on the original editor from [Nexus Mods](https://www.nexusmods.com/farfarwest/mods/5).

This project adds zh_HK support, and a standalone Windows build.

## Features

- Open, edit, and save Far Far West `.save` files.
- Drag and drop support on Windows.
- Built-in presets for common edits such as money, item levels, upgrades, unlocks, and challenges.
- Manual editing of parsed save fields in the GUI.
- CLI tools for decrypting, parsing, packing, and round-tripping saves.
- Standalone `.exe` build available, so Python is not required for end users.

## Getting Started

### Run the GUI from source

```bash
python save_editor_gui.py
```

### Open a save file

You can open a save with the Open button or drop a `.save` file anywhere on the window.

Default save folder:

```text
C:\Users\[Username]\AppData\Local\FarFarWest\Saved\SaveGames
```

The editor derives the AES key from the save filename. The filename must begin with the SteamID prefix used by the game.

### Save changes

- Use Save to overwrite the current file.
- Use Save As to write a copy.
- When overwriting, the GUI writes a timestamped `.backup_gui_*.save` backup next to the original file.
