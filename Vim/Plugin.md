= Vim Plugin Setup =

    == General setup ==
        1. Install plugin manager _vim-plug_ from https://github.com/junegunn/vim-plug
            * Automate install (copy-paste content under section _Vim_ for Powershell).
        2. Enter new plugin in __vimrc_ -> Execute `:PlugInstall` to install.
        3. To upgrade _vim-plug_ execute `:PlugUpgrade`.
        4. To update all plugins execute `:PlugUpdate`.
        5. To remove a specific plugin:
            a) Delete/comment out the plugin entry in __vimrc_.
            b) Execute `:PlugClean` -> Say 'y' to delete directory prompt.
        6. To check status of all plugins execute `:PlugStatus`.

    == Flake8 setup (for Ale plugin) ==
        * Store configuration file _.flake8_ in _$HOME_.

    == Tagbar setup ==
        Build ctags using the following steps:
            a) Install build packages first:
               `$sudo apt install gcc make pkg-config autoconf automake python3-docutils libseccomp-dev libjansson-dev libyaml-dev libxml2-dev`
            b) Create folder named _Ctags_ in ~/Documents/
            c) Clone repo in ~/Downloads: `$git clone https://github.com/universal-ctags/ctags.git`
            d) `$cd ctags`
            e) `$./autogen.sh`
            f) `$./configure --prefix=/home/roy/Documents/Ctags`
            h) `$make && make install`
            i) Delete ctags repo in ~/Downloads

    == Color Scheme setup (without using plugin) ==
        * Color scheme files are stored in _~/.vim/colors_ and _lightline_ files are in _~/.vim/autoload/lightline_
        * Move new plugin color scheme file in corresponding locations and add necessary customizations:
            * Add long line alert code at the end of each theme file in _~/.vim/colors_
            * Add needed tweaks near the beginning of _gruvbox8_ and _onedark_ scheme files in _~/.vim/colors_

    == Snippets setup ==
        * Loading these two plugins in console vim prevents the window to scale up. To bypass this:
            * Put _resize.vim_ file in _$HOME\vimfiles\after\plugin_.

