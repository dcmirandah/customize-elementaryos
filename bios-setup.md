# BIOS setup for XPS 13 9300
- Change the SATA Mode from the default "RAID" to "AHCI" (already the default on the developer edition). This will allow Linux to detect the NVME SSD. If dual booting with an existing Windows installation, Windows will not boot after the change but this can be fixed without a reinstallation.
- Disable secure boot to allow Linux to boot (already the default on the developer edition).
- For reliable resumption from sleep, disable both Sign of Life options, i.e. set Early Logo Display and Early Keyboard Backlight to OFF.

_Source: https://wiki.archlinux.org/index.php/Dell_XPS_13_(9300)#UEFI_
