# LEDMonitor
For UNIX Systems Administration and Programming Semester 2 2018  
Code checked April 2020

# Background
More information is available in the README.txt file.

This program was coded and tested on a Raspberry Pi 3B and can be used on Linux systems. No installation is required.

When run, the program reads the contents of the /sys/class/leds directory and can be used to control the LEDs connected to your device.

The program can also control LEDs to monitor the memory or CPU usage of the program. However, this is experimental and there is no guarantee that it will work perfectly.

# How to run
Run the command `./led_config`. You may need to `chmod 777` both `led_config` and `led_monitor` to do so.