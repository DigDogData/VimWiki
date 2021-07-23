= R install (for Linux Mint 20) =

    == On LM20 ==
        1. Add GPG key: `sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9`
        2. Add repo: `sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'`
        3. Update packages: `sudo apt update`
        4. Install R: `sudo apt install r-base`

    == On LMDE4 ==
        1. Add GPG key: `sudo apt-key adv --keyserver keys.gnupg.net --recv-key 'E19F5F87128899B192B1A2C2AD5F960A256A04AF`
        2. Add repo: `sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/debian buster-cran40/'`
        3. Update packages: `sudo apt update`
        4. Install R: `sudo apt install -t buster-cran40 r-base`
