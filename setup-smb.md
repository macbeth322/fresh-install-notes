1. install `samba`
2. enable `smb` service to enable smb
3. enable `nmb` service to enable discovery of the smb server
4. [configure /etc/samba/smb.conf](./configs/etc/samba/smb.conf)
5. add samba user
 - `smbpasswd -a windows`
 - `smbpasswd -a shield`
6. As of "samba 4.7.6-1", I get a memory leak when running on the rPi
    1. copy over /etc/systemctl/system/restart-samba.{timer,service}
    2. enable the timer `systemctl enable restart-sambda.timer`
