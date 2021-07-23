= HDDTemp setup =

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
