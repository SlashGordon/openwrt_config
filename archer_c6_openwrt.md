# Archer c6 
## install openwrt with tftp
sudo apt-get install tftpd-hpa

wget http://downloads.openwrt.org/releases/19.07.2/targets/ath79/generic/openwrt-19.07.2-ath79-generic-tplink_archer-c6-v2-squashfs-factory.bin

sudo mv openwrt-19.07.2-ath79-generic-tplink_archer-c6-v2-squashfs-factory.bin /var/lib/tftpboot/ArcherC6v2_tp_recovery.bin

sudo chown tftp:tftp /var/lib/tftpboot/ArcherC6v2_tp_recovery.bin

sudo nano /etc/default/tftpd-hpa
```
TFTP_USERNAME="tftp"
TFTP_DIRECTORY="/var/lib/tftpboot"
TFTP_ADDRESS=":69"
TFTP_OPTIONS="--secure --create"
```

sudo systemctl restart tftpd-hpa

sudo systemctl status tftpd-hpa

Set local ip to 192.168.0.66. Restart Archer C6, press reset and wps button for 10 sec.

Wait...
