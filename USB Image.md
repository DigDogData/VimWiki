= Write iso image to USB stick =

    1. Check USB stick drive (*/dev/sdx* as in drive, not /dev/sdxy as in partition):
       `sudo blkid`
    2. Write image (input file path can be relative):
       `sudo dd bs=4M status=progress oflag=sync if=/path/to/file.iso of=/dev/sdx`
