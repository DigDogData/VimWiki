= Pipenv setup =

    == Install Pipenv (on linux) ==

        1. First install _pip3_: `sudo apt install python3-pip`
        2. Next install _Pipenv_: `pip3 install pipenv`
        3. Add virtualenv path _~/.local/bin_ to _.bashrc_ with
            `echo 'export PATH="$PATH:$HOME/.local/bin"' >> ~/.bashrc`
        4. Source shell: `exec "$SHELL"`

    == Install Pipenv (on windows) ==

        1. _pip_ comes bundled with python.
        2. Run command prompt as administrator.
        3. Execute `pip install pipenv`
        4. Path already included (_pipenv_ is installed in _python_ path).

    == Create Environment ==

        1. Go to project directory (e.g. _HandsOnML_):
            `cd ~/Documents/Data_Science/HandsOnML`
        2. Create environment with specified python version (installed with _pyenv_):
            `pipenv --python 3.8.6`
        3. Allow pre-release package install (add these lines in _Pipfile_):
            [pipenv]
            allow_prereleases = true
        4. Install packages:
            a) Dev packages: `pipenv install --dev black flake8`
            b) Production packages: `pipenv install pandas scikit-learn matplotlib seaborn`
            In case of warning 'Could not find a version that matches...':
                a) First rerun install with `--skip-lock`:
                   `pipenv install --dev --skip-lock black flake8`
                b) Next lock with `--pre --clear`:
                   `pipenv lock --pre --clear`
        5. Activate environment with `pipenv shell`.
        6. Deactivate simply with `exit`.
        7. Alternatively, run command within environment without activating it:
           `pipenv run python Chapter8/chapter8_1.py`
        *  Install packages from _requirements.txt_ with:
           `pipenv install -r /path_to_requirements.txt`
        *  Create new _requirements.txt_ file with
           `pipenv lock -r > requirements.txt`
        *  To install package in dev environment (not to ship to production):
           `pipenv install <packagename> --dev`
           (adds to _Pipfile_'s _[dev-packages]_ list)
        *  To uninstall packages: `pipenv uninstall <packagename>`
        *  To change python version, say to 3.6:
            1. First edit _Pipfile_: `python_version = "3.6"
            2. Next install with `pipenv --python 3.6`
        *  To check package integrity, run `pipenv check`
        *  To update package version (fo example if suggested from `pipenv check`):
            1. Edit _Pipfile_ to modify the package version
            2. Run `pipenv install` to update package(s).
        *  View package dependencies with `pipenv graph`.
        *  When ready for production:
            1. Update _Pipfile.lock_ with `pipenv lock`
            2. Recreate VE in production environment using _Pipfile.lock_:
               `pipenv install --ignore-pipfile`   # ignores _Pipfile_

    == Remove environment but keep package list ==
        1. Go to pipenv project directory (e.g. _HandsOnML_):
            `cd ~/Documents/Data_Science/HandsOnML`
        2. `pipenv --rm`
        3. To re-create environment using same _Pipfile_, just run `pipenv install`

    == Remove environment completely ==
        1. Go to pipenv project directory (e.g. _HandsOnML_):
            `cd ~/Documents/Data_Science/HandsOnML`
        2. `pipenv --rm`
        3. `rm Pipfile*`

    == Update pipenv ==
        Run `pip install --upgrade pipenv`

    == Uninstall pipenv ==
        1. Run `rm -rf ~/.local/share/virtualenv*`
        2. Run `pip3 uninstall pipenv`
        3. Purge package *python3_pip*: `sudo apt purge python3-pip`
        4. Remove *pipenv* path from _.bashrc_
        5. Quit and restart shell.

