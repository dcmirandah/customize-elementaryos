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
