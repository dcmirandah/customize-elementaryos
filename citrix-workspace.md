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
