# Useful software
- `sudo apt install gnome-disk-utility`
- `sudo apt install gnome-system-monitor`
- `sudo add-apt-repository ppa:kasra-mp/ubuntu-indicator-weather` and `sudo apt-get install indicator-weather`

## Express vpn
https://www.expressvpn.com/support/vpn-setup/app-for-linux/#install

## indicator-sysmonitor
https://github.com/fossfreedom/indicator-sysmonitor

```
vim myipgeo.sh
  #!/bin/bash
  geolocation=$(expressvpn status | grep 'Connected\|connected')
  geolocation=$geolocation | sed -n 's/Connected to / /'
  echo $geolocation | sed 's/\x1b\[[0-9;]*m//g'
chmod +x myipgeo.sh
```
