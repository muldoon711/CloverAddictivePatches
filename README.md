# CloverAddictivePatches

A collection of many toggleable quality-of-life improvements for CloverPit. Tweak FOV, skip repetitive dialogues, peek into drawers, and smooth out rough edges.

## Installation

1. **Install BepInEx** (if you haven't already)
   - Download [BepInEx 5 x64](https://github.com/BepInEx/BepInEx/releases) — get the `BepInEx_win_x64_*.zip`
   - Extract it into your CloverPit game folder (same folder as `CloverPit.exe`)
   - Run the game once, then close it — this creates the `BepInEx/plugins/` folder

2. **Install the mod**
   - Go to [Releases](https://github.com/muldoon711/CloverAddictivePatches/releases) and download `CloverAddictivePatches_v*.zip`
   - Extract the zip — it will produce a `BepInEx/plugins/CloverAddictivePatches.dll` structure
   - Drag that `BepInEx` folder into your CloverPit game folder (merge, don't replace)
   - **Or** just copy `CloverAddictivePatches.dll` directly into `BepInEx/plugins/`

3. **Launch and configure**
   - Start CloverPit
   - Press Esc in-game → Settings → scroll to the bottom → **Mod Options**

## How to Use Each Feature

### Transition Speed (Extended)
The game has a built-in Transition Speed setting that controls how fast round animations play. Normally it caps at 4x. With this mod installed it goes up to **16x**.

- Press **Esc** → Settings → scroll to **Transition Speed**
- Press left/right (or A/D on controller) to change the value — it now wraps from 16x back to 1x
- This is one of the most noticeable features for faster gameplay

### Adjustable FOV
- **F1** — decrease FOV | **F2** — increase FOV (range: 60–110°)
- Or go to Esc → Settings → Accessibility → **FOV** (new option added by the mod)
- Or set it in Mod Options

### Drawer Peek
Automatic — just hover your cursor over a drawer and it opens slightly so you can see what's inside without fully committing to opening it. Move your cursor away and it closes.

### Quick Swap (Inventory ↔ Drawer)
When you inspect an equipped item (click on it in your inventory), the context menu will have extra **"Swap with [Item]"** entries — one for each drawer slot that has something in it. Selecting one instantly swaps the equipped item into that drawer and the drawer item into your inventory.

### Smart Deposit
When you're at the ATM depositing coins, hold **Shift** while pressing the deposit button. Instead of depositing one step at a time, it calculates and deposits as much as possible in one click — stopping automatically just before the crown (debt paid) or skull warning (too broke to spin) threshold.

### Instant Restart
Automatic. When you restart via the R button hold or the in-game Restart option, the death camera animation is skipped and you go straight to the black screen/stats.

### Skip Repetitive Warnings
Automatic when enabled. Skips the "1 round left" warning dialogue and the "welcome back" dialogue on subsequent runs.

### Reduced Skip Delays
Automatic when enabled. You can skip dialogues and cutscenes almost immediately instead of waiting 0.5 seconds for the skip to become available.

### No Vertigo Effects
Off by default — enable in Mod Options. Removes the dolly zoom, scary camera look, and falling death animation. Useful if those effects cause motion sickness.

### Quiet Drawers
Automatic when enabled. Suppresses the horror sound and FOV jump that plays when you open a drawer containing skeleton parts.

### ATM Cutscene Freeroam
Off by default — enable in Mod Options. Lets you move the camera freely during the ATM/interests cutscene instead of being locked to the cinematic view.

### New Run Confirmation
Automatic when enabled. If your save has any progress, starting a new game shows a confirmation dialog so you can't accidentally wipe your run.

### Memory Card Menu Access
Automatic when enabled. You can open the main menu (Esc) during the Memory Card selection screen, which lets you quit the game without consuming a card.

### Skip Intro
On by default (in Debug settings). The game's startup/intro sequence is skipped automatically.

## Mod Options Menu
Almost everything can be toggled live without restarting the game:
- Press **Esc** in-game → Settings → scroll to the bottom → **Mod Options**
- Changes apply immediately

For settings not shown in Mod Options, edit `BepInEx/config/io.github.failspy.qualityclover.cfg` and restart.

## Troubleshooting

- **Mod not loading / nothing happens?** Check `BepInEx/LogOutput.log`. Make sure BepInEx is installed and initialized (you should see a console window when the game launches). Make sure `CloverAddictivePatches.dll` is in `BepInEx/plugins/` — not in a subfolder inside plugins.
- **Specific feature not working?** Check Mod Options to confirm it's enabled. Some features (No Vertigo, ATM Freeroam) are off by default.
- **Game updated and mod broke?** Check [Releases](https://github.com/muldoon711/CloverAddictivePatches/releases) for a new version. If none is available yet, file an issue.

## Building From Source

### Windows

1. Install [Visual Studio Build Tools](https://visualstudio.microsoft.com/downloads/) (free — scroll down to "Build Tools for Visual Studio")
2. Clone this repo
3. Run `compile.bat` from Command Prompt or PowerShell

The script auto-detects your CloverPit Steam installation. If it can't find it, override:
```cmd
set CLOVERPIT_DIR=D:\SteamLibrary\steamapps\common\CloverPit
compile.bat
```

The compiled DLL is copied to `BepInEx/plugins/` automatically.

### Linux / WSL

```bash
sudo apt install mono-mcs   # Debian/Ubuntu
./compile.sh
```

Override game path if needed:
```bash
CLOVERPIT_DIR="/path/to/CloverPit" ./compile.sh
```

## Changelog

### v1.0.7 — 2026 Game Update Compatibility

Restored compatibility after the CloverPit 2026 update.

- Fixed accessibility menu layout: game now provides Flashing Lights natively (shifted mod-injected FOV option from index 5 to 6)
- Fixed `Data.settings` access: game changed it from a field to a property
- Fixed `PowerupScript.NameGet()`: gained a third `sanitize` parameter in the update
- Version bump 1.0.6 → 1.0.7

### v1.0.6 and earlier

See [commit history](https://github.com/muldoon711/CloverAddictivePatches/commits/main).
