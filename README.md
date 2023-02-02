# synergy3-beta-steamdeck
Run Synergy 3 Beta on Steam Deck

Symless have launched their beta version of Synergy 3 available on several different distros, with a missing one being Arch Linux.

<div style="text-align:center"><img src="https://m.jrdn.dev/LuHu3t1K" /></div>

## Prerequisites
- You have beta access to Synergy 3. 
- SteamOS readonly mode is turned off using `sudo steamos-readonly disable`
- If you have not set a sudo password, you should set one now.
- You have up-to-date pacman keys, as well as the archlinux keys. To do this, run the following commands:
   ```
   # sudo pacman -Sy archlinux-keyring
   # sudo pacman-key --init
   # sudo pacman-key --refresh-keys
   ```

## Installing on Steam Deck
1. Boot into Desktop Mode on Steam Deck
2. Download the synergy 3 zip from the [releases](https://github.com/jordanwalster/synergy3-beta-steamdeck/releases) in this repo.
3. Extract the zip to a folder of your choice.
4. Open the zip in your terminal. 
5. Copy the `.so.3` files to `/usr/lib`:
   ```
   sudo cp *.3 /usr/lib
   ```
6. Install Synergy
   ```
   sudo pacman -U synergy-3-beta.pkg.tar.zst
   ```
   Import any requested PGP keys.
7. Launch Synergy 3.
8. Set steamos readonly filesystem to enabled
   ```
   sudo steamos-readonly enable
   ```

## Removing Synergy
You can uninstall Synergy by running: `sudo pacman -R synergy`

## Troubleshooting
You may find that when you initially boot up Synergy, that it fails to load the background service. If this happens it should only show for a few seconds and then you should see a green tick appear, with the option to continue into the application.

<div style="text-align:center"><img src="https://m.jrdn.dev/RG_feGuu" /></div>

If you see an error similar to the one below, this can be safely ignored. Synergy will run without issues after clicking 'Dismiss'.

<div style="text-align:center"><img src="https://m.jrdn.dev/dkBg5Zu8" /></div>