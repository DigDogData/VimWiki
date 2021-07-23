= Lutris set up =

    == Installation ==

        1.  Enable 32bit architecture (should be enabled by default):
            `sudo dpkg --add-architecture i386`
        2.  Download Wine's repository key:
            a) `wget -nc https://dl.winehq.org/wine-builds/winehq.key`
            b) `sudo apt-key add winehq.key`
        3.  Add Wine repository (for LM20.1):
            `sudo add-apt-repository 'deb https://dl.winehq.org/wine-builds/ubuntu/ focal main'`
        4.  Update: `sudo apt update`
        5.  Install Wine (stable): `sudo apt install --install-recommends winehq-stable`
        6.  Add Lutris PPA: ` sudo add-apt-repository ppa:lutris-team/lutris`
        7.  Update: ` sudo apt update`
        8.  Install Lutris: ` sudo apt install lutris`
        9.  If Lutris doesn't launch (launch from CL to see errors), add _dxvk_:
            `wget https://cdn.discordapp.com/attachments/538903130704838656/796102070825779250/dxvk_versions.json -P $HOME/.local/share/lutris/runtime/dxvk`
        10. If Lutris is stuck at "Lutris is starting...", disable IPv6 systemwide:
            a) Edit _sysctl.conf_ file in sudo mode: `sudo xed /etc/sysctl.conf`
            b) Add following three lines at the end:
                `net.ipv6.conf.all.disable_ipv6 = 1`
                `net.ipv6.conf.default.disable_ipv6 = 1`
                `net.ipv6.conf.lo.disable_ipv6 = 1`
            c) Save and exit
            d) Run `cat /proc/sys/net/ipv6/conf/all/disable_ipv6`
            e) If it gives `1`, IPv6 is disabled; if `0`, IPv6 is still on (Continue to next step)
            f) Run `sudo sysctl -p`
            g) Repeat Step d) above.
