= Managing dotfiles =

    1. Create git repo named _.dotfiles_ under `$HOME`
    2. Install GNU _stow_ package: `sudo apt install stow`
    3. Move all essential configuration files to _.dotfiles_ repo following proper procedure
    4. Run `cd .dotfiles`
    5. Run `stow */` to create all dotfile symlinks
    6. Update remote git repo with `git push`
