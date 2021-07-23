= SCID vs PC Setup =

    == Install SCID ==
        1. Download latest source package from http://scidvspc.sourceforge.net/
        2. Unzip in ~/Downloads folder
        3. `sudo apt update && sudo apt upgrade`
        4. If not pre-installed, install g++ compiler and tcl/tk dev packages:
            `sudo apt install g++ tcl-dev tk-dev`
        5. Go to install folder and sequentially execute:
            a) `./configure`
            b) `make`
            c) `sudo make install` (installs scid in /usr/local/bin/)
            d) Delete downloaded install folder

    == Install Stockfish engine ==
        1. Download latest (zipped) file from https://github.com/official-stockfish/Stockfish
        2. Extract to '~/Documents/Games/Chess/' folder
        3. Go to '~/Documents/Games/Chess/Stockfish-master/src' folder
        4. Compile:
            a) `make help`
            b) `make net`
            c) `make build ARCH=x86-64-modern`
        5. `sudo cp stockfish /usr/local/bin`
        6. Add Stockfish to SCID:
            a) `Tools -> Analysis Engines -> New`
            b) Add Name and Command (leave other fields unchanged)
            c) Move Stockfish to the top of the list
            d) Delete other pre-loaded engines (else Stockfish is not chosen as default - bug?)

