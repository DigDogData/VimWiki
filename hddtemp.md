= HDDTemp setup =

    == Add HDD temp monitor to xfce sensors-plugin (Linux Mint 20) ==
    1. `cd /etc/default`
    2. `sudo cp hddtemp hddtemp.orig`
    3. `sudo nano hddtemp`
        * `RUN_DAEMON="true"`
        * `Ctrl-x -> y` (save -> exit)
    4. _hddtemp.service_ requires root privilege -> dirty hack (has security risk):
        * `sudo chmod u+s /usr/sbin/hddtemp`
    5. Set monitor color to `#00ff00`
    6. Reboot

    == For Manjaro ==
    1. Install hddtemp: `sudo pacman -S hddtemp`
    2. Edit _hddtemp.service_:
        a) `sudo systemctl edit hddtemp.service`
        b) Paste the following lines between 2nd and 3rd commented line:
           -----------------------------------------
           [Unit]
           Description=Hard drive temperature monitor daemon
           [Service]
           ExecStart=
           ExecStart=/usr/bin/hddtemp -dF /dev/sda
           [Install]
           WantedBy=multi-user.target
           -----------------------------------------
        c) Save (Ctrl-O) and exit (Ctrl-X)
    3. Start/stop/restart hddtemp service:
        `sudo systemctl start hddtemp`
        `sudo systemctl stop hddtemp`
        `sudo systemctl restart hddtemp`
    4. Check status of hddtemp: `systemctl status hddtemp`
    5. Enable hddtemp at boot: `sudo systemctl enable hddtemp`
    6. Enable & start hddtemp: `sudo systemctl enable --now hddtemp`
    7. Disable hddtemp at boot: `sudo systemctl disable hddtemp`
