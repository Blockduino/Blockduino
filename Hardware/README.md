# Blockduino

## Features Overview

Blockduino comprises a carrier board with a soldered Atmel SAMA5D27 SOM1 module. The module features a
SAMA5D27-D1G-CU SIP embedding a 1-Gbit DDR2 SDRAM. 

The SOM  module integrates a 1-Gbit DDR2 SDRAM, a QSPI memory and a 10/100 Mbps Ethernet controller.
128 GPIO pins are provided by the SOM for general use in the system. All GPIO pins are independent
and can be configured as inputs or outputs, with or without pull-up/pull-down resistors.

The carrier board features a wide range of peripherals, as well as a user interface and expansion options,
including one mikroBUS™ click interface headers to support over 300 MikroElektronika click boards™.

#### SAMA5D27 SOM1 Features

The system of the SAMA5D27 SOM1 operates at a maximum CPU operating frequency of 500 MHz and
a maximum bus speed of 166 MHz. The SAMA5D27 SOM1 is a 176-pin, 0.8mm pad pitch module with a 40mm x 38mm size.

It features:
* ARM Cortex-A5 processor (SAMA5D27)
* 1 Gbit of DDR2 SDRAM memory (SAMA5D27C-D1G-CU)
* 2 Kb serial E2PROM with preprogrammed EU-48 node identity (24AA02E48T-I/OT)
* 64 Mb of QSPI Flash (SST26VF064BT-104I/MF) memory
* Power management device (MIC2800)
* Ethernet Phy 10/100 MHz RMII (KSZ8081RNA)

#### Carrier Board Features

| Characteristics        | Specifications                      | Components                            |
|------------------|----------------------------------|-------------------------------------
| Ethernet |   One Ethernet interface        | RJ45 connector |
| USB Com Port  |  One USB device        | Connector type microAB |
| CAN |  One CAN interface        |ATA6561 |
| Video |   One ISC 12-bit interface        |2x15 male connector |
| Display |   One LCD RGB 24-bit interface        | 50-pin FPC connector|
| Debug port  |  One JTAG interface        | Tag-Connect adapter |
| Security |  One tamper connector        | 10-pin male connector |
| Expansion |   One mikroBUS interface       | 2x8-pin female connector |
| Expansion |   One Pmod connector       | 6-pin female connector |

## Communication Interfaces

#### Ethernet  10/100 (GMAC) Port

The on-board SOM integrates a 10/100 Mbps Ethernet controller (KSZ8081RNA) allowing direct
connection to any 10/100 Mbps Ethernet-based Local Area Network, for full interaction with local servers
and wide area networks such as the Internet.

ETH signals from the SOM are connected to a RJ45 MagJack. Additionally, for monitoring and control
purposes, a LED functionality is carried on the RJ45 connector to indicate link status.

RJ45 connector

#### USB-A Device Interface

The carrier board provides a USB Type A Device interface. 

The USB-A port is used as a secondary power source and as a communication link for the carrier board, and derives power from the host over the USB cable. In most cases, this port is limited to 500 mA.

USB-A MicroAB connector

#### CAN Interface

The CAN interface transmits and receives signals from the SOM. CAN PIOs PC26 and PC27 are
connected to the CAN transceiver (ATA6561) and the output signals from the transceiver are connected
to the screw connector physically located on top of the carrier board.

3-pin screw terminal

## External Interfaces


####  LCD TFT Interface
The carrier board provides a FPC connector with 24 bits of data and control signals to the LCD interface.
Other signals are used to control the LCD and are available on connector Jxx: TWI, SPI, two GPIOs for
interrupt, 1-wire and power supply lines.

This connector is used to connect LCD display type TM43xx series or TM7000 series from [PDA Inc](www.pdaatl.com).
A 50-pin FPC (Jxx) header is provided on the baseboard to interface the LCD module with 24-bit parallel
RGB. The connector provides two PIOs as interrupts, one SPI and a TWI port to interface the MaXTouch touch
controller or QTouch button controller embedded on the LCD module.

Suitable LCD is the [Digikey 1230-1007-ND](https://www.digikey.com/products/en?keywords=1230-1007-ND).

50-pin FPC connector

#### Image Sensor (ISC) Interface

The Image Sensor Controller (ISC) system manages incoming data from a parallel or serial CSI-2 based
CMOS/CCD sensor. The system supports a single active interface, as well as the ITU-R BT 656/1120 422
protocol with an 8-bit or 10-bit data width and raw Bayer format. 
The internal image processor includes adjustable white balance, color filter array interpolation, color correction, gamma correction, 12-bit to 10-bit compression, programmable color space conversion, as well as horizontal and vertical chrominance subsampling module.

2x15-pin male connector

## Board Monitor

#### RGB LED
The carrier board features one RGB LED which can be controlled by the user. The three LED cathodes are
controlled via GPIO PWM or timer/counter pins.

#### Push Buttons
The carrier board features three push buttons switches physically located on top of the board: 
Reset, Wakeup, User.

## Programmable Input/Output (PIO)

The carrier board includes numerous peripherals. Many of these are connected to the GPIO block so that
the I/O pins can be configured to carry out many alternative functions. This provides great flexibility to
select a function multiplexing scheme for the pins that satisfy the interface need for a particular
application.

#### PIOBU Interface
The carrier board features one tamper connector with eight tamper pins for static or dynamic intrusion detection, UART reception, and two analog pins for comparison. For a description of intrusion detection, refer to the SAMA5D2 datasheet, chapter "Security Module".

10-pin male connector

#### mikroBUS Interfaces
The carrier board hosts one pair of 8-pin female headers acting as mikroBus interfaces. The
mikroBUS standard defines the main board sockets and add-on boards (a.k.a. "click boards") used for
interfacing microprocessors with integrated modules with proprietary pin configuration and silkscreen
markings. The pinout consists of three groups of communication pins (SPI, UART and TWI), four
additional pins (PWM, interrupt, analog input and reset) and two power groups (+3.3V and GND on the
left, and 5V and GND on the right 1x8 header).

2x8-pin female headers

#### Flexcom PMOD Interface
Pmod devices are Digilent’s line of small I/O interface boards that offer an ideal way to extend the
capabilities of programmable logic and embedded control boards. They allow sensitive signal conditioning
circuits and high-power drive circuits to be placed where they are most effective - near sensors and
actuators.

6-pin connector

#### TWI Interface

Molex 4-pin snap-in connector

(from unused mikroBus header)

#### UART 

4-pin male connector

(from unused mikroBus header)

## Debugging Capabilities
The carrier board includes one JTAC debugging interface to provide debug-level access to the SAMA5D2.

#### Debug JTAG

A 10-pin JTAG header is provided on the carrier board to facilitate software development and debugging
using various JTAG emulators. The interface signals have a voltage level of 3.3V.

10-pin header for Tag-Connect adapter [TC2050-IDC](http://www.tag-connect.com/TC2050-ARM2010).

