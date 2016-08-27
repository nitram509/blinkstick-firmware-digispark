Compile and upload firmware
---------------------------

You need to install the Arduino tools as described in the
[Digispark tutorial: 'Connecting and Programming Your Digispark'](http://digistump.com/wiki/digispark/tutorials/connecting) first.

````
make clean
make hex
/opt/arduino-1.5.8-64bit/hardware/digistump/avr/tools/avrdude -cdigispark --timeout 30 -Uflash:w:main.hex:i
````

BlinkStick Firmware
-------------------

BlinkStick is a DIY open source USB RGB LED. It's small, the
size of a USB flash stick and designed to be easy to assemble.

You can find more details about it here:

http://www.blinkstick.com

This repository contains the firmware required for the ATTiny85 chip.

Details about setting up the development environment will be released soon.

License
-------

Released under CC-BY-NC-SA 3.0 license:

http://creativecommons.org/licenses/by-nc-sa/3.0/

(c) 2013 by Agile Innovative Ltd
