= Mouse/Keyboard wakeup =

    1. Find USB port by mouse/keyboard brand: `dmesg | grep /input/ | grep Logitech`
    2. Check USB power status: `grep . /sys/bus/usb/devices/*/power/wakeup`
    3. Enable wakeup for mouse/keyboard:
        `echo enabled | sudo tee /sys/bus/usb/devices/3-1.2/power/wakeup`
        `echo enabled | sudo tee /sys/bus/usb/devices/3-1.3/power/wakeup`
    4. Recheck USB power status: `grep . /sys/bus/usb/devices/*/power/wakeup`
