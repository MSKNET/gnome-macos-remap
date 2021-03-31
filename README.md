# Gnome → macOS Keyboard Remap

<figure>
  <img src="https://github.com/petrstepanov/gnome-macos-remap/blob/master/resources/gnome-macos-remap.png?raw=true" alt="Gnome macOS Remap Icon" />
</figure>

Migrating to Linux from a Mac? This bash script remaps native GNOME desktop environment keybindings to the macOS defaults. Very useful keyboard remap for Linux users who are running GNOME on a Macbook, Mac or a PC with Apple keyboard. Don't spend time getting used to the default GNOME keybindings. Run the script and use your Linux just like you do use your Mac. Here are some key remaps that are implemented:

* Command key `⌘` set as main system modifier key.
* Copy and Paste work in Terminal with `⌘ c`, `⌘ v`. Regular interrupt `ctrl c` works in Terminal.
* Nautilus keyboard hotkeys replaced with the Finder ones: navigate in and out of folder, delete folder, new folder...
* Home and End keys assigned to macOS defaults `⌘ ←` and `⌘ →`.
* Workspace switching works with `Ctrl ←` and `Ctrl →`.
* Some macOS window manager keyboard shortcuts are implemented: application switcher `⌘ tab`, `⌘ ~`, close window `⌘ w`.
* Mission Contol <img src="https://help.apple.com/assets/5E59C74D0946226F03EEDC17/5E59C7520946226F03EEDC2C/en_US/0a3719d8c9acde3a43680efa67ef11a2.png" alt="the Mission Control key" height="16px"> and Launchpad <img src="https://help.apple.com/assets/5E59C74D0946226F03EEDC17/5E59C7520946226F03EEDC2C/en_US/d6924e805b6d1a255218f1307a96ef25.png" alt="the Launchpad key" height="16px"/> media keys are remapped.
* And more...

## How does it work?
The functionality is based on the Autokey mechanism. On top of that the default GNOME shell keybindings are modified as well. Therefore it will only work in X11 window system. Wayland is not supported.

## Prerequisities
Make sure you are using X11, not Wayland. Logout from your session. On the GNOME login screen find and click gear icon. Select option "GNOME on Xorg". Log back in.

Install `autokey`, `autokey-gtk` and `git` packages with the package manager of your chioce. On Debian based distribution (Ubuntu, Pop!, )run `sudo apt-get install git autokey autokey-gtk`. On Fedora run `sudo dnf install git autokey autokey-gtk`.

## Installation
Check out the repository to an arbitrary location and run the `install.sh` script in Terminal. Script will ask for administrator password.

```
git clone https://github.com/petrstepanov/gnome-macos-remap
cd gnome-macos-remap
sh install.sh
```

Open AutoKey preferences and make sure the "Automatically start AutoKey at login" checkbox is on. 
System restart is required in order for the remap to start working.

## Postinstall tips
To get a functionality similar to the macOS Spotlight, I recommend installing the [Ulauncher application](https://ulauncher.io/). You can assign the `⌘ space` hotkey for the Ulauncher in its settings.

## How to uninstall
Navigate into the program directory in Terminal and run `uninstall.sh`.

## Rodmap
Some hotkeys need to be implemented on the application-specific basis. However a [regexp-related issue](https://github.com/autokey/autokey/issues/161) in Autokey prevents doing it at the moment. More macOS hotkeys will be implemented once this issue is resolved.
