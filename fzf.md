= Set up fzf =

    1. Install (using git):
        a) `git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf`
        b) `~/.fzf/install`
    2. Install vim plugin (updates fzf and adds extra vim features):
        `Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }`
        `Plug 'junegunn/fzf.vim'`
    3. Install _ripgrep_: `sudo apt install ripgrep`
    4. Configurations in _.bashrc_ and _.vimrc_ should work automatically
    5. Update fzf (via vim): `:PlugUpdate`
    6. Uninstall:
        a) Uninstall vim plugin: Deactivate `Plug` -> Run `:PlugUninstall`
        b) Uninstall fzf: `~/.fzf/uninstall`

