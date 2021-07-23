= Set up Conda Environments =

    1. Create empty environment _ds39_ (for default python version 3.9): `$conda create -n ds39 -y`.
    2. Activate this env: `$conda activate ds39`.
    3. Confirm added _conda-forge_ channel and strict priority:
        a) `$conda config --show channels`.
        b) `$conda config --show channel_priority`.
    4. Install packages:
        a) Data science:
            `$conda install pandas scikit-learn matplotlib seaborn py-xgboost python-wget -y`.
        b) Web development:
            `$conda install django -y`.
        c) Linter/formatter: `$conda install black flake8 -y`.
        d) Python/pdb tab completion (windows only): `$conda install pyreadline -y`.
    * To create environment _ds38_ with a different python version:
        - `$conda create -n ds38 python=3.8 -y`.
    * To remove environment _ds38_:
        a) Deactivate this env: `$conda deactivate ds38`.
        b) Remove: `$conda remove -n ds38 --all -y`.

