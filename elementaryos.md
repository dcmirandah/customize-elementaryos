# BIOS setup for XPS 13 9300
- Change the SATA Mode from the default "RAID" to "AHCI" (already the default on the developer edition). This will allow Linux to detect the NVME SSD. If dual booting with an existing Windows installation, Windows will not boot after the change but this can be fixed without a reinstallation.
- Disable secure boot to allow Linux to boot (already the default on the developer edition).
- For reliable resumption from sleep, disable both Sign of Life options, i.e. set Early Logo Display and Early Keyboard Backlight to OFF.

_Source: https://wiki.archlinux.org/index.php/Dell_XPS_13_(9300)#UEFI_

# Elementary tweaks
- `sudo add-apt-repository ppa:philip.scott/elementary-tweaks`
- `sudo apt install elementary-tweaks`
_Source: https://github.com/elementary-tweaks/elementary-tweaks_

## Enable dark mode
- Replace the file at `/usr/share/dbus-1/interfaces/io.elementary.pantheon.AccountsService.xml` with the contents of https://github.com/elementary/default-settings/blob/master/accountsservice/io.elementary.pantheon.AccountsService.xml
_Source: https://elementaryos.stackexchange.com/questions/24874/dark-theme-not-working-in-system-settings_

# Show system tray
- `sudo add-apt-repository ppa:yunnxx/elementary`
- `sudo apt install indicator-application wingpanel-indicator-ayatana`
- edit the file `/etc/xdg/autostart/indicator-application.desktop`: `OnlyShowIn=Unity;GNOME;Pantheon;`
- `sudo mv /etc/xdg/autostart/nm-applet.desktop /etc/xdg/autostart/nm-applet.old`
_Source: https://www.reallinuxuser.com/how-to-show-app-indicators-on-the-system-tray-in-elementary-os/_

# Useful software
- `sudo apt install gnome-disk-utility`
- `sudo apt install gnome-system-monitor`

# libinput gestures
```
# Add yourself to the input group
sudo gpasswd -a $USER input

# Install dependencies
sudo apt-get install xdotool wmctrl libinput-tools

# Clone and install
git clone http://github.com/bulletmark/libinput-gestures
cd libinput-gestures
sudo ./libinput-gestures-setup install

touch ~/.config/libinput-gestures.conf
sudo vim ~/.config/libinput-gestures.conf
    # Gestures
    gesture swipe up 3 xdotool key super+Down
    gesture swipe down 3 xdotool key super+Down
    gesture swipe left 3 xdotool key super+Right
    gesture swipe right 3 xdotool key super+Left

libinput-gestures-setup restart
libinput-gestures-setup autostart
```
_Source: https://github.com/bulletmark/libinput-gestures and https://neal.codes/blog/adding-mac-like-touch-gestures-to-elementary-os_

# Express vpn
https://www.expressvpn.com/support/vpn-setup/app-for-linux/#install


# System Cleanup
```
sudo apt-get autoclean # clean partial packages using a command
sudo apt-get clean # auto cleanup apt-cache
sudo apt-get autoremove # clean up of any unused dependencies
```

# Citrix installation
```
# Download deb file: https://www.citrix.com/downloads/workspace-app/linux/workspace-app-for-linux-latest.html
sudo gdebi icaclient_19.10.0.15_amd64.deb
sudo ln -sf /etc/ssl/certs/* /opt/Citrix/ICAClient/keystore/cacerts/ # Certificate error

# Download HDX engine for Skype for business: https://www.citrix.com/fr-fr/downloads/citrix-receiver/additional-client-software/hdx-realtime-media-engine-latest.html
sudo unzip -q HDX_RealTime_Media_Engine_2.9_for_Linux_x64.zip
cd HDX_RealTime_Media_Engine_2.9_for_Linux_x64
sudo chmod +x HDXRTME_install.sh
sudo vim HDXRTME_install.sh 
    1419 if [ -r '/etc/os-release' ]; then
    1420     os="Debian"
sudo ./HDXRTME_install.sh
```