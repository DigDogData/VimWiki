= pyenv set up =

    == On linux ==

        1. Install *pyenv*: `git clone https://github.com/pyenv/pyenv.git ~/.pyenv`
        2. Define environment variable *PYENV_ROOT* and add path:
            a) `echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc`
            b) `echo 'export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc`
        3. Add *pyenv init* to shell (to enable shims and autocompletion):
           `echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bashrc`
        4. Restart shell to update path: `exec "$SHELL"`
        5. Confirm install: `pyenv --version`

    == On Windows ==

        1. To install pyenv, run on git-bash: `git clone https://github.com/pyenv-win/pyenv-win.git $HOME/.pyenv`
        2. Add *PYENV* and *PYENV_HOME* to environment variables:
            * Control Panel -> System and Security -> System -> Advanced system setting -> Environment Variables -> System variables -> New:
                * Name: *PYENV* -> Value: _C:\Users\Admin\.pyenv\pyenv-win_
                * Name: *PYENV_HOME* -> Value: _C:\Users\Admin\.pyenv\pyenv-win_
        3. Add pyenv path:
            * Control Panel -> System and Security -> System -> Advanced system setting -> Environment Variables -> Environment variables -> Path -> Edit -> New:
                * _%PYENV%\bin_
                * _%PYENV%\shims_
            * Move both paths above \path_to_WindowsApps.
        4. Close and reopen terminal -> Run `pyenv --version` confirm setup.

    == Update pyenv (on linux) ==
        1. Run `cd $(pyenv root)`
        2. Run `git pull`

    == Uninstall pyenv (on linux) ==
        1. Run `rm -rf ~/.pyenv/`
        2. Run `rm -f ~/.local/bin/virtualenv*`
        3. Run `rm -rf ~/.local/lib/python*`
        4. Purge python dependency packages installed from list above.
        5. Remove *pyenv* path and init lines from _.bashrc_
        6. Quit and restart shell.

    == Install python using pyenv (on linux) ==

        1. First check to see if pyenv already installed any python version: `pyenv versions` (note plural)
           For Linux Mint 20 (system python3 is not detected _as python_ by pyenv):
                a) Install *python-is-python3* package (symlinks /usr/bin/python to python3): `sudo apt install python-is-python3`
                b) Next run `pyenv versions`
        3. Install python build dependencies:
            `sudo apt install libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev llvm libncurses5-dev libncursesw5-dev tk-dev liblzma-dev python-openssl -y`
        4. Check available python versions: `pyenv install --list`
        5. Install python 3.8.6: `pyenv install 3.9.6`
        6. Confirm with `pyenv versions`
        7. After installing a new python version, run 'rehash' command to update shims: `pyenv rehash`
        8. Use this python version locally (in current shell):
            a) `pyenv local 3.8.6` (creates a temporary file _.python-version_ in '$HOME')
            b) Confirm with `python --version`
        9. Use this version globally (in all shells): `pyenv global 3.8.6`
        10. Go back to system default: `pyenv global system`
        11. Remove local python version: `pyenv local --unset`
        12. Set shell-specific python version (overwrites global setting): `pyenv shell 3.8.6`
        13. Unset shell: `pyenv shell --unset`
        14. Uninstall a python version (w/o confirmation): $pyenv uninstall -f <version>`

    == Install python using pyenv (on Windows) ==

        1. Check available python versions: `pyenv install --list`
        2. Install latest python (3.8.2): `pyenv install 3.8.2`

