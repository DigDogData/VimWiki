= Vim Installation =

    == On Linux Mint ==
        1. Install vim: `sudo apt install vim`
        2. Enable clipboard support (if `:version` shows *-clipboard*):
           `sudo apt install vim-gtk`

    == On Windows ==
        1. Get signed *gVim* from https://github.com/vim/vim-win32-installer/releases
            (scroll down for signed copy for 64-bit package).
        2. Install *gVim*.
        3. Start *gVim*:
            * Type `:version` to check _python3/dyn_ support for python38 version.
            * `:echo has('python3')` and `:echo has('python3_dynamic')` must return `1`.
        4. Copy _vimrc_ file from _$HOME\Documents\Data Analysis\Basics_ to _$HOME_:
            a) Rename it __vimrc_.
            b) Appropriately modify `let using_PC= ` near the top of this file.
        5. Create folders _backupdir_ and _undodir_ in _$HOME\vimfiles_.
        6. Add vim path to use console vim:
            Control Panel -> System and Security -> System -> Advanced system settings ->
            Environmental Variables -> Edit _User Path_ -> _New_ -> Add _C:\Program Files\Vim\vim82_.

