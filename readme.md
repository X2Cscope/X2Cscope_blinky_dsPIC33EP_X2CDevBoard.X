# MPLAB X Project: X2Cscope_blinky_dsPIC33EP_X2CDevBoard

This is a X2Cscope demo project for [X2C+ Development board](http://x2c.microstickplus.com/) and [dsPIC33EP256MC502](https://www.microchip.com/wwwproducts/en/dsPIC33EP256MC502) microcontroller that is selectable. 

The purpose is to demonstrate the [X2Cscope firmware based debugger tool](https://x2cscope.github.io/) features like run-time watch and scope views.

The code functionality is minimalistic in order to avoid unneceseary confusion. It is generating internally a digital sawtooth and a sine signal. There is LED1 that is blinking with the sawtooth signal's period. The LED2 can be controlled manually by the [X2Cscope run-time debugger tool](https://x2cscope.github.io/). The state of the SW1 can be read out by X2Cscope.

![HW setup](doc/Hardware.gif)
![X2Cscope](doc/Scope_Animated.gif)

## Getting Started

The demo is ready to use with the [listed hardwares below](#hardware).

1. Clone or Download zipped project.
2. [Connect Hardware](#connectors-used).
3. Open project with MPLAB X
4. Build project
5. Program the HW with the PICkit on board
6. Verify if LED1 is blinking

## Use X2Cscope

The X2Cscope tool using the UART to transfer data from and to the HW. To use this feature follow the steps:

1. Verify if X2Cscope plug-in is installed within MPLAB X. Detailed user guide: https://x2cscope.github.io/
2. Open X2Cscope 

![Open X2C MCC](doc/open_X2Cscope.png)

3. Verify UART settings at the Connection Setup tab and also check the COM port number on the PC. (device manager)

4. Connect to the HW with clicking on the connect sign: 

![Open Button](doc/Connect_X2Cscope.png)

6. Use the data views

## Hardware

* [**X2C dev board:**](http://x2c.microstickplus.com/) Low voltage motor control development board with [dsPIC33CK256MC502](https://www.microchip.com/wwwproducts/en/dsPIC33CK256MC502) MCU 

### Connectors used:

![Block Diagram](doc/BlockDiagram_HW_Setup.png)

* **PGM (USB:** PICkit on board 3 (PKOB3) programmer/debugger
* **COM USB-UART:** MCP2200 USB-UART chip is used for X2Cscope run-time debugging. MCU<->PC 

### Configuration

X2C+ dev board is used in the default configuration.  

## Peripheral settings and I/O connections: 

**UART:**
   * Baud rate: 115200
   * Parity: None
   * Data bits: 8
   * Stop bits: 1
   * Flow control: no

**TIMER1:**
   * 1ms period
   * interrupt enabled

**IO**

| PIN | PORT   | Function |
| ----|--------|----------|
|  11 | RB4    | UART1 TX |
|  12 | RA4    | UART1 RX |
|  15 | RB6    | IO_LED1  |
|  16 | RB7    | IO_LED2  |
|  17 | RB8    | IO_LED3  |
|  18 | RB9    | IO_LED4  |
|   9 | RA2    | IO_SW1   |
|  10 | RA3    | IO_SW2   |

   Peripherals are configured by [MCC](https://microchipdeveloper.com/mcc:mccgpio) according to the X2C+ board [schematics](http://x2c.microstickplus.com/).

   If you need more details of peripheral configuration, just open MPLAB X then MCC with the MCC button:  
   ![MCC Button](doc/MCC_Button.jpg)

## Software

To use the demo only the MPLAB X IDE and XC16 compiler is required. 

* [MPLAB X](https://www.microchip.com/mplab/mplab-x-ide) Integrated Development Environment. 
* [XC16 Compiler:](https://www.microchip.com/mplab/compilers) Compiler for the Microchip 16bit MCUs
## Built With

* [XC16 v1.61](https://www.microchip.com/mplab/compilers) - Microchip C compiler for 16bit micros
* [MCC v4.0.2](https://www.microchip.com/mplab/mplab-code-configurator) - Configure peripherals and generate low level drivers
* [X2Cscope v0.5](https://mchp-x2cscope.github.io/) - Run-time firmware based debugger tool