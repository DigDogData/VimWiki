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
