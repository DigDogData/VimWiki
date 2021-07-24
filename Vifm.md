= Vifm set up =

    1. Install _vifm_ with `sudo apt install vifm`
    2. Set up icons:
        a) Install _Hack_ Nerd fonts:
            I)   Copy _~/Downloads/NerdFonts/_ folder to _~/.local/share/fonts_ (create folder if absent)
            II)  Run `fc-cache -fv` to update font cache
            III) Check font install with `fc-list | grep Hack`
            IV)  Set terminal default font to 'Hack Nerd Font Regular' via Preferences->Appearance->Font
            V)   Edit _~/.dotfiles/vifm/.config/vifm/vifmrc_ to add _file Types_ properties from https://q2a.vifm.info/269/how-to-add-icons
        b) Check preview by going to https://www.nerdfonts.com/cheat-sheet and copy-pasting any icon to terminal
    3. Set up preview:
        a) Copy _vifmimg_ and _vifmrun_ scripts from https://github.com/cirala/vifmimg to _~/.dotfiles/vifm/.config/vifm/scripts_
        b) Edit _vifmrun_ (next-to-last line) to include _vifmimg_ path
        c) Make these scripts executable with `chomd a+x <filename>`
        d) Set alias (in _.bashrc_) to run _vifm_ via _vifmrun_: `alias vf='~/.config/vifm/scripts/vifmrun .'`
        e) Edit _~/.dotfiles/vifm/.config/vifm/vifmrc_ to add _fileviewer_ properties from https://github.com/cirala/vifmimg
        f) Install _Ueberzug_ (python package) with `pip install ueberzug`
        g) Install _ImageMagick_ (for image preview):
            I)    Download latest source files (to _~/Downloads/Apps/ImageMagick/_) with `wget https://www.imagemagick.org/download/ImageMagick.tar.gz`
            II)   Extract with `tar xvzf ImageMagick.tar.gz`
            III)  Navigate to extracted folder: `cd ImageMagick-7.0.11-8/`
            IV)   `./configure`
            V)    `make`
            VI)   `sudo make install`
            VII)  `sudo ldconfig /usr/local/lib` (to configure runtime bindings of ImageMagick)
            VIII) Check install with `magick --version`
            IX)   (To uninstall, run `sudo make uninstall` from extracted folder)
        h) _ffmpegthumbnailer_ (for video preview) already installed in LM20
        i) _pdftoppm_ (for pdf preview) already installed (as part of _poppler-utils_ package) in LM20
        j) Install _ffmpeg_ (for audio info preview): `sudo apt install ffmpeg`
        k) Install _fontpreview_ (for font preview):
            I)   Clone repo (in _~/Downloads/Apps/FontPreview/_) with `git clone https://github.com/sdushantha/fontpreview`
            II)  `cd fontpreview`
            III) `sudo make install`
        l) Install _epub-thumbnailer_ (for epub preview):
            I) Can't install _install.py_ script (perhaps it works only in Gnome?)
