## To return to original firmware (uninstall Gargoyle) - Tested with TP-Link WR741ND:

* 1: Download latest firmware from tp-link 
(with "boot" in its name, ex.: "wr741nv4_en_3_16_6_up_boot(130524).bin"). 
* 2: Download a app called "winscp517".
* 3: Download a app called "putty".
* 4: With "winscp", login (SCP mode) as: 
```
hostname: 192.168.1.1 (or one you configured in connection - lan)
username: root
password: (if you have created in gargoyle or default "password")
```
and copy the firmware file to "tmp" folder

* 5. Open PuTTY as SSH to 192.168.1.1 and perform the following commands:
```bash
cd tmp
dd if=TL-WR840Nv5_VN_0.9.1_3.16_up_boot[170517-rel46524].bin of=tplink.bin skip=257 bs=512 

mtd -r write /tmp/tplink.bin firmware
# and wait until flash complete!
```



main firmware file

lede-ramips-mt76x8-tl-wr840n-v5-squashfs-tftp-recovery.bin

renamed firmware file

tp_recovery.bin

i userd tftp on windows 
Link: http://tftpd32.jounin.net/tftpd32_download.html
file name tftpd64.exe

firstly i tried to flash official firmware with tftp
>previosly i have opended
