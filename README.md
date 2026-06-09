# Far Far West Save Editor

Save editor for [Far Far West](https://store.steampowered.com/app/3124540/_Far_Far_West/), based on the original editor from [Nexus Mods](https://www.nexusmods.com/farfarwest/mods/5).

This project is a fork from the [Github Release](https://github.com/old-cookie/farfarwest_save_editor) of Old-Cookie who added zh_HK support and a standalone Windows build.

Compile locally or use this projects' standalone Windows build.

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

## Transferring your save to another steam account
### Prerequisites
- Find your save file at `C:\Users\[Username]\AppData\Local\FarFarWest\Saved\SaveGames\[your steam64 ID].save`
- Obtain the `Steam64 ID` of both accounts (for example by using SteamID finder)
- Start the game on the other account and create a backup (Options -> Backups -> create Backup)
- This should create a timestamped `backup.sav` file

### How to transfer
- Close the game
- Open the save you want to transfer
- Click on the *Transfer To Account* dialogue
- Enter the `Steam64 ID` of the account you want to transfer to
- Save it as the previously created `backup.sav` file and overwrite it
- Start the game and load it from the in-game "recover from backup" dialogue

### My save does not open/is corrupted
- Disable steam cloud save before trying to import?
- You entered a wrong Steam ID while saving to file-> the game tries to derive a cipherkey from the `Steam64 ID.save` file name.
- The process of backup loading has been altered