# RPi.GPIO.64

This is a modification of the original RPi.GPIO code to add 64bit OS support.

The idea of this modification is the detection of the revision and model of the raspberry pi on
64 bit operation systems using the Device Tree instead of the older method (reading the cpuinfo).

Tested on RPi3b but in theory will work with any model of raspberry pi.

*PLEASE* dont report bugs to the original maintainer!

### Installation
Download and install as local package or install from github directly:
```
pip install git+https://github.com/TheNextLVL/RPi.GPIO.64.git
```

### Tips [RPi 3b]
I recomend the usage of the kernel of [sakaki](https://github.com/sakaki-/bcmrpi3-kernel) (work in any 64bit OS).

Check that the group `gpio` exists and the current user (usually `pi`) belong to that group.

Check that any user has the correct permissions to the device `/dev/gpiomem` (`crw-rw----`) and
belongs to `root:gpio` --> [more info](https://www.raspberrypi.org/forums/viewtopic.php?t=221127#p1363771)

## Original README file
This package provides a class to control the GPIO on a Raspberry Pi.

Note that this module is unsuitable for real-time or timing critical applications.  This is because you
can not predict when Python will be busy garbage collecting.  It also runs under the Linux kernel which
is not suitable for real time applications - it is multitasking O/S and another process may be given
priority over the CPU, causing jitter in your program.  If you are after true real-time performance and
predictability, buy yourself an Arduino http://www.arduino.cc !

Note that the current release does not support SPI, I2C, hardware PWM or serial functionality on the RPi yet.
This is planned for the near future - watch this space!  One-wire functionality is also planned.

Although hardware PWM is not available yet, software PWM is available to use on all channels.

For examples and documentation, visit http://sourceforge.net/p/raspberry-gpio-python/wiki/Home/
