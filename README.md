# synergy3-beta-steamdeck
Run Synergy 3 Beta on Steam Deck

Symless have launched their beta version of Synergy 3 available on several different distros, with a missing one being Arch Linux.

![Synergy 3 on Steam Deck](https://m.jrdn.dev/LuHu3t1K "Synergy 3 on Steam Deck")

## Prerequisites
- SteamOS readonly mode is turned off using `sudo steamos-readonly disable`
- You have up-to-date pacman keys, as well as the archlinux keys. You can run:
  - `sudo pacman -Sy archlinux-keyring`
  - `sudo pacman-key --init`
  - `sudo pacman-key --refresh-keys`

## Steps to install on Steam Deck:
1. Boot into Desktop Mode on Steam Deck
2. Download the synergy 3 zip from the [releases](https://github.com/jordanwalster/synergy3-beta-steamdeck/releases) in this repo.
3. Extract the zip to a folder of your choice.
4. Go to the `/usr/lib` folder.
5. Check that there are no files that may be overwritten by the contents of the zip.
   - `ls /usr/lib | grep libssl`
   - `ls /usr/lib | grep libcrypto`
6. If none of the file names match, Copy the `.so` files to `/usr/lib`
   - `sudo cp *.3 /usr/lib`
7. Install the synergy 3 package
   - `sudo pacman -U synergy-3-beta.pkg.tar.zst`
   - Import the required PGP keys.
8. Launch Synergy 3.
9. Set steamos readonly filesystem to enabled
   - `sudo steamos-readonly enable`

## Removing Synergy
You can uninstall Synergy by running: `sudo pacman -R synergy`

## Troubleshooting
You may find that when you initially boot up Synergy, that it fails to load the backend service. Give it a moment and it should eventually pass.
![Synergy 3 Error 1](https://m.jrdn.dev/RG_feGuu)
