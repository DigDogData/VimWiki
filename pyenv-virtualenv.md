= pyenv-virtualenv setup =

    1. Install *pyenv-virtualenv* plugin: `git clone https://github.com/pyenv/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv`
    2. Check installed python versions: `pyenv versions`
    3. Create environment (e.g. with python version 3.8.6) inside working directory: `pyenv virtualenv 3.8.6 venv38`
    4. List existing virtualenvs: `pyenv virtualenvs`
    5. Activate virtualenv (inside working directory): `pyenv activate venv38`
    6. Deactivate virtualenv: `pyenv deactivate`
    7. Delete virtualenv: `pyenv uninstall venv38`

