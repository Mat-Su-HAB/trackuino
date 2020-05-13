![Banner](https://github.com/trackuino/trackuino/wiki/img/trackuino-banner-narrow.png)

This is the firmware for Trackuino, an open-source APRS tracker based on the Arduino platform. It was designed primarily to track high altitude balloons, so it has other handy features like reading temperature sensors and a buzzer for acoustic location.

Trackuino is intended for use by licensed radio amateurs.

Features
========

 * Arduino shield form factor (you can stack more shields on it)
 * GPS: Venus 638FLPx. Reports okay above 18 Km.
 * Radio: Radiometrix's HX1 (300 mW).
 * 1200 bauds AFSK using 8-bit PWM
 * Sends out standard APRS position messages (latitude, longitude, altitude, course, speed and time).
 * Internal/external temperature sensors (LM60) to read temperature in and outside the payload
 * Active/passive buzzer support to ease acoustic payload location.
 * 2 x SMA female plugs (1 x GPS in + 1 x radio out)
 * Open source (GPLv2 license), both software and hardware. In other words, do whatever you want with it: modify it, add it to your project, etc. as long as you opensource your modifications as well.

Dependencies
============

You will need to install [PlatformIO](https://platformio.org/) to build and
upload the firmware.

There are required [udev rules](https://docs.platformio.org/en/latest/faq.html#platformio-udev-rules)
for Linux users.

Building
========

Simply run `platformio run` from the project root.

The single most important configuration file is "config.h". The file is self-documented. Here is where you set up your callsign, among other things.

Flashing
========

While connnected via serial to your Arduino, run `platformio run --target upload` from the repository root.

**Important**: When flashing the Arduino/Uno32, remove the Venus GPS or the entire Trackuino shield. After flashing the firmware, you can plug it back in. The GPS and the host computer share the same serial port on the AVR, so they will conflict when used together.

Hardware
========

The [Trackuino shield](https://github.com/trackuino/shield) repository contains the Eagle schematic / pcb files of a shield you can build as-is (gerber files are included) or modify to suit your needs. Check its README for details.
