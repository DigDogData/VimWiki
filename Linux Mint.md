= Linux Mint odds and ends =

    * Search for user-installed packages:
        - Recently installed packages: `grep install /var/log/dpkg.log | grep <packagename>`
        - Older packages: `zgrep install /var/log/dpkg.log.x.gz | zgrep <packagename>` (x=1,2,..)
