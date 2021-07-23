= Samba set up =

    1. Install samba: `$sudo apt update` -> `$sudo apt install samba`
    2. Check samba status: `$systemctl status smbd`
    3. copy _smb.conf_ from _/home/roy/Documents/Scripts_ to _/etc/samba_:
        a) `$cd /etc/samba`
        b) `$sudo mv smb.conf smb.conf.bak`
        c) `$sudo cp ~/Documents/Scripts/smb.conf .`
    4. Reboot samba: `$sudo service smbd restart`
