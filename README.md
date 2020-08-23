Why this fork?
===============

This fork aims to make the Blinkstick.com firmware run on the 
[Digispark](http://digistump.com/products/1) USB development board.

### Compile and upload firmware

You need to install the Arduino tools as described in the
[Digispark tutorial: 'Connecting and Programming Your Digispark'](http://digistump.com/wiki/digispark/tutorials/connecting) first.

#### Build the firmware

For building the firmware there's a Makefile available.
Please, cross-check the first lines in the Makefile, so that your local Arduino paths match. 

````
make clean
make hex
````

#### Flashing with Arduino 1.6.x

Flashing the firmware to the microcontroller requires the above mentioned Digispark plugins installed.
With Arduino 1.6.x the following command let you flash the .hex file.
This method is outdated and does not work anymore with current OSX (by May 2020).
It might work with older Linux releases still. I recommend switching to Arduino 1.8.x variant below.

````
/opt/arduino-1.5.8-64bit/hardware/digistump/avr/tools/avrdude -cdigispark --timeout 30 -Uflash:w:main.hex:i
````

#### Flashing with Arduino 1.8.x

With Arduino 1.8.x some changes where made and flashing the ATTiny85 is different now,
because of an updated toolchain. 

(Example OSX)
````
~/Library/Arduino15/packages/digistump/tools/micronucleus/2.0a4/launcher -cdigispark --timeout 30 -Uflash:w:main.hex:i
````

#### Change number of LEDs

In the ```main.cpp``` file, you can define the number of LEDs,
e.g. when you wabt to connect a [Neopixel](https://www.adafruit.com/category/168)

```cpp
#define NUMBER_OF_LEDS   64
```

### Images

![Digispark USB with custom soldered WS2812 LED shield](/pictures/IMG_20150310_234954_117.jpg?raw=true)
![Red and Green LED on Digispark USB and custom WS2812 LED shield, with Mark Minion](/pictures/IMG_20150310_235913_781.jpg?raw=true)

BlinkStick Firmware
===================

BlinkStick is a DIY open source USB RGB LED. It's small, the 
size of a USB flash stick and designed to be easy to assemble. 
    
You can find more details about it here:

http://www.blinkstick.com

This repository contains the firmware required for the ATTiny85 chip.

Details about setting up the development environment will be released soon.


License
=======

Released under CC-BY-NC-SA 3.0 license:

http://creativecommons.org/licenses/by-nc-sa/3.0/

(c) 2013 by Agile Innovative Ltd
