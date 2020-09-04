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
