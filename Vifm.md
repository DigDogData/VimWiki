= Vifm set up =

    1. Install _vifm_ with `sudo apt install vifm`
    2. Set up icons:
        a) Install _Hack_ Nerd fonts:
            I) Copy _~/Downloads/NerdFonts/_ folder to _~/.local/share/fonts_ (create folder if absent)
            II) Run `fc-cache -fv` to update font cache
            III) Check font install with `fc-list | grep Hack`
        b) Check preview by going to https://www.nerdfonts.com/cheat-sheet and copy-pasting any icon to terminal
    3. Set up image preview (does not work yet):
        a) Install w3m packages with `sudo apt install w3m w3m-img`
        b) Edit files _~/.config/vifm/scripts/imgt_ and _~/.config/vifm/scripts/imgc_ to add correct
            _w3mimgdisplay_ path _/usr/lib/w3m/w3mimgdisplay_
