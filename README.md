# WiSense WSN Platform :  README

This file contains all the device IDs and parameters pertaining to the devices used in **Wisense WSN Platform**. Each device will need a unique ID, 
and this ID has to be matching with the code on hardware as well.
For example '0x08' represents a device ID of 8.

## Getting Started

The following descriptions will explain about Device IDs, ID allocation and their specifications

## (1) Device IDs:
Each device(RFD) will have an ID allocated in the software. This ID is traced to establish a connection with that particular RFD. 
Here, the allocation starts from 0x01 to 0xff, with few IDs unused in random and will be defined as Dummy.
```c
For example:
0x0 - 0 - Dummy
0x1 - 1 - PLTFRM_AT24C01C_1_DEV_ID - EEPROM AT2401C ATMEL // Device ID 0x1 or 1
```
>###### [AT24C01C(Device ID 0x1)Datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-8700-SEEPROM-AT24C01C-02C-Datasheet.pdf)

## (2) ID allocation:
Device IDs are allocated in hex formats, starting from 0x00 to 0xff. This practice is followed in order to reduce the complexity with more numbers in the
program as there is large no: of devices in the network. 
```c
For example:
0xa - 10 - PLTFRM_TMP102_1_DEV_ID - TMP102 - TI  // Device ID 0xa or 10
```
>###### [TI TMP102(Device ID 0xa)Datasheet](http://www.ti.com/lit/ds/symlink/tmp102.pdf)
```c             
0x59 - 89 - PLTFRM_INA219_1_SV_DEV_ID - TI I2C Out Current/Power Monitor INA219 // Device ID 0x59 or 89                        
```
>###### [TI INA219(Device ID 0x59)Datasheet](http://www.ti.com/lit/gpn/ina219)

## (2) Device/component name and make:
In the following documentation, ***device name, description*** and ***manufacturer*** will be specified in the ***forth block*** in a line, in the order following the
*device ID in HEX*, *device ID in decimal*, and the *device macro definition*, respectively. 
```c
For example:
0xa - 10 - PLTFRM_TMP102_1_DEV_ID - TMP102 on the chip Temperature from TI  // Device ID 0xa or 10
```
Here the various identifiers in a line are:

>(1)0xa                    :The device ID in hex format.

>(2)10                     :The device ID in decimal.

>(3)PLTFRM_TMP102_1_DEV_ID :Device macro definition in the program.

>(4)TMP102 on the chip Temperature sensor from TI : Device/component name, description and manufacturer.

