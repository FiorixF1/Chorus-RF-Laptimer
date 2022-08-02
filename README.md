# Chorus RF Laptimer

This is a fork of the original [Chorus](https://github.com/voroshkov/Chorus-RF-Laptimer) intended to work on an Arduino board with processor Atmega32U4 instead of Atmega328, such as Arduino Micro or Sparkfun Pro Micro.

The patch consists of the following modifications:
- References to LED on pin 13 commented out (the Micro has no built-in LED).
- Replaced the ```Serial``` object with ```Serial1```: Serial is used to communicate to the host PC through USB, but the Bluetooth module needs Serial1 to communicate.
- Aligned the ```fastReadWrite.h``` module to the pin mapping of the Atmega32U4: that module was highly dependent on the pin configuration of the chip.
- Updated pin assignment for the Micro board:
    - SPI Data (CH1) on pin 10
    - Slave Select (CH2) on pin 16
    - SPI Clock (CH3) on pin 14
    - RSSI on pin A3
    - Voltage monitor on pin A0
    - Buzzer on pin 9
- The firmware still needs a 5 V board and a 16 MHz processor ;)

