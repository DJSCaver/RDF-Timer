# RDF Timer
When using a cave RDF system sometimes it is necessary to setup the in cave transmitter before the surface receiver is ready to be used.
For example the only surface receiver operator may be the person setting up the in cave RDF transmitter. In this case in order to save Tx battery
power it is necessary to delay the start of the RDF Tx to a time that the RDF Rx operator is on the surface.
# Basics
The RDF Timer is based on the following through-hole components:
* ATMega128P-PU : Microchip 8-bit AVR micro 128 KB flash, 4 KB EEPROM, 16 KB SRAM
* Real Time Clock module (RTC) : with AT24C32 EEPROM IIC I2C Module. Remove the 200 ohm battery charge resistor
* OLED Display : White 64x128 pixels OLED display, I2C, 0.96-inch, SSD1306 driver
* LM4040 : Adafruit Precision LM4040 Voltage Reference 4.096V Module
* LCA110L : Optical Relay
* DSP1a-L2-DC5V : Dual coil magnetic Latching Relay
* PCB : Size less that 100 x 100mm to meet the Asian $5 for five boards. This required manual cutting of delivered board into two for main board/front panel board.
* Assorted through-hole support components (resistors, diodes, capacitors, push buttons, headers)
* 3D printed case
* Arduino Sketch firmware
# Variations
The basic design can be changed into various versions:
* Base Version - Latching Relay power control with battery voltage monitor.
* MOSFET Version - External Power control via Low-Side MOSFET module. No onboard Latching Relay. Cheaper due to low cost MOSFET modules.
* Dual Latching Relays - Supports two external battery connections. Firmware checks No-Load battery voltage to choose which battery to connect to RDF TX.
# On/Off Time Setting
* The Arduino Sketch supports the setting of three possible SLOTS of start and end times to control output power.
![Fig1](https://github.com/user-attachments/assets/6a8a9a1b-71ff-449f-9439-2993d3a09bc9)
* An ON/OFF time is defined with MONTH, DAY, HOUR, MINUTE
![Fig2](https://github.com/user-attachments/assets/589ce89b-d39f-4699-8eac-30bc1151b341)
