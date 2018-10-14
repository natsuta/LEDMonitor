INTRODUCTION
-------------------------
The LED Configuration Menu allows you to control the LEDs manually or according to system events.
The LEDs can also be used to monitor the performance of a process, namely the process' usage of memory or CPU. However, this is an experimental program and there is no guarantee that it will work 100%.

DETAILS
-------------------------
There is no installation or configuration required for this program. When run, this program automatically reads the contents of the /sys/class/leds directory, detecting all LEDs connected to your device, whether it be built-in or connected via other means (like the NumLock/CapsLock/ScrollLock LEDs on your keyboard).

The turning on and off of the LEDs is done in a matter as such:
echo [0/1] | sudo tee /sys/class/leds/[LED]/brightness >/dev/null
where 0 turns the LED off and 1 turns it on.

The /sys/class/leds/[LED]/trigger file is also used to associate an LED with a system event. The triggers are echoed into a list (you may have to scroll or maximise your screen) and when one is selected, the trigger is echoed back into the trigger file.

PROCESS MONITORING
-------------------------
As stated, this is an experimental program and there is no guarantee that it will work 100%. The program name is input and searched through ps before it is passed onto a background script.

The program can monitor either the program's memory usage or CPU usage on one LED each time the script is triggered. Triggering another instance of that program will kill the previous instance.

The LED will light up for a percentage of a second relative to the program's memory or CPU usage before it goes off for the remainder of that second (or at least, that's what it should do theoretically).

This process repeats until the script is killed, whether by deactivating it manually or by triggering another instance of that program (which will automatically kill the previous instance).