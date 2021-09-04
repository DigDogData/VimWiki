= Samba set up =

    1. Install samba: `sudo apt update` -> `sudo apt install samba`
    2. Check samba status: `systemctl status smbd`
    3. Copy _smb.conf_ from _/home/roy/Documents/Scripts/Configs_ to _/etc/samba_:
        a) `cd /etc/samba`
        b) `sudo mv smb.conf smb.conf.bak`
        d) `sudo cp ~/Documents/Scripts/smb.conf .`
    4. Test config: `testparm`
    5. Retart samba: `sudo systemctl restart smbd` -> `systemctl status smbd`
    6. Allow samba in firewall: `sudo ufw allow samba`
    7. Mount samba:
        a) `sudo mkdir /mnt/pc`
        b) Temporary mount:
           `sudo mount -t cifs -o credentials=~/.smbcred,uid=roy,gid=roy //pc-3.local/roy /mnt/pc`
           Unmount: `sudo umount /mnt/pc
        c) Permanent mount:
           I) `sudo xed /etc/fstab`
           II) Add lines at the end (make sure last line is blank):
               `# samba mount on /mnt/pc`
               `//pc-3.local/roy /mnt/pc cifs credentials=/home/roy/.smbcred,uid=roy,gid=roy 0 0`
           III) Update fstab after each reboot (mount samba in thuner first):
                `sudo mount -a`
