= Install Miniconda =

    == Linux ==

        1. Copy and run the following codes sequentially from home (`~/`):
            a) Create Miniconda directory: `$md -p ~/miniconda3`
            b) Download latest shell script:
               `$wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh`
            c) Run script (point to Miniconda folder): `$bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3`
            d) Remove script: `$rm -f ~/miniconda3/miniconda.sh`
            e) Add following lines to *.bashrc*:
               `source ~/miniconda3/etc/profile.d/conda.sh`
               `if [[ -z ${CONDA_PREFIX+x} ]]; then`
                  `export PATH="~/conda/bin:$PATH"`
               `fi`
        2. Restart shell: `$exec "$SHELL"`

    == Windows ==

        1. Download *Miniconda* from https://docs.conda.io/en/latest/miniconda.html
        2. Install *Miniconda* (check box to add path).

    == Post-install setp (Linux and Windows) ==

        3. Add _conda-forge_ channel with `conda config --env --add channels conda-forge`.
            * Confirm with `conda config --show channels`.
        4. Change channel priority with `conda config --env --set channel_priority strict`.
            * Confirm with `conda config --show channel_priority`.

