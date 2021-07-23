= Git Setup =

    == Config ==
        * `git config --list --show-origin` - _View all Git settings_
        * `git config --global user.name 'DigDogData'` - _Set user name_
        * `git config --global user.email 'roy@manojitroy.com'` - _Set user email_

    == Commands for local repo ==
        * `git init` - _Initalize repo_
        * `git add .` - _Add all files to Index (staging area)_
        * `git commit -m 'commit message'` - _Commit changes in Index_
        * `git status` - Check status of working tree
        * `git rm --cached <file>` - _Remove file from Index_
        * `git branch <branchname>` - _Create a branch_
        * `git checkout <branchname>` - _Switch to branch (from master)_
        * `git merge <branchname>` - _Merge changes to master_

    == Commands for remote (github) repo ==
        * To link existing local repo to remote repo:
            1. Create empty remote repo.
            2. Go to local repo directory.
            3. Run `git remote add origin <git-URL>`
            4. Run `git push -u origin master`
        * To clone remote repo:
            1. Go to one level above local repo path.
            2. Run `git clone <git_URL>`
        * `git push` - _Push to remote repo_
        * `git pull` - _Pull from remote repo_

    == To ignore file/folder from being committed ==
        1. Create empty file _.gitignore_.
        2. Add file/folder name to _.gitignore_.

    == Customize Git Bash (on Windows) ==
        1. Create folder _$HOME\.config\git_.
        2. Copy _git-prompt.sh_ from _$HOME\Documents\Data Analysis\Basics\Git_.
        3. Cop _bashrc_ from _$HOME\Documents\Data Analysis\Basics\Git_ to _$HOME_.
        4. Rename this file _.bashrc_.
        5. Start Git Bash -> Ignore bash_profile warning.
        6. Change R-G-B color values to 40-42-54.
        7. Choose font and layout size as suited.
