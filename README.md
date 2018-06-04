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
program due to a large number of devices in the network.
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


#### NB: A link to datasheet is provided after every device description.

### Please refer back the above [Getting started](https://github.com/pjmahesh/Readme.md/blob/master/README.md#getting-started) for any clarifictions required in reading the program:

```c
/*
 * File Name : pltfrm.h
 * Author : ram krishnan
 * Created : 10/21/2013
 * Documentation for Pltfrm.h
*/
#ifndef __PLTFRM_H__
#define __PLTFRM_H__
// --------------------- Devices -------------------------- 
// This contain all the device IDs and parameters pertaining to the devices in Wisense WSN Platform.
// Each device will need a unique ID, and this ID has to be matching with the code on hardware as well
// Eg., 0x8 represnets a device ID value of 8 
/*
/*
 * Device ID hex value : Decimal Value : Macroname :  Description
 * 0x0 - 0 - Dummy
 * 0x1 - 1 - PLTFRM_AT24C01C_1_DEV_ID - EEPROM AT2401C ATMEL
 *           http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-8700-SEEPROM-AT24C01C-02C-Datasheet.pdf
 * 0x2 - 2 - PLTFRM_AT24MAC602_1_DEV_ID - EEPROM AT24MAC402 ATMEL
 *           http://ww1.microchip.com/downloads/en/DeviceDoc/Atmel-8807-SEEPROM-AT24MAC402-602-Datasheet.pdf
 * 0x9 - 9 - PLTFRM_LM75B_1_DEV_ID - LM75B - NXP
 *           https://www.nxp.com/docs/en/data-sheet/LM75B.pdf
 * 0xa - 10 - PLTFRM_TMP102_1_DEV_ID - TMP102 - TI
             http://www.ti.com/lit/ds/symlink/tmp102.pdf
 * 0xb - 11 - PLTFRM_NTC_THERMISTOR_1_DEV_ID - Vishay - NTCALUG02A (analog)
 *           https://www.vishay.com/docs/29094/ntcalug02a.pdf
 * 0xc - 12 - PLTFRM_NTC_THERMISTOR_2_DEV_ID - Vishay - NTCALUG02A (analog)
 * 0xd - 13 - PLTFRM_NXFT15XH103_1_DEV_ID - Murata - NXFT15XH103 (analog)
 *            https://www.murata.com/~/media/webrenewal/support/library/catalog/products/thermistor/ntc/r44e.ashx
 * 0xe - 14 - PLTFRM_NXFT15XH103_2_DEV_ID - Murata - NXFT15XH103 (analog)
 * 0xf - 15 - (Dummy) PLTFRM_DNAX300R103L040_1_DEV_ID - 
 * 0x10 - 16 - (Dummy) PLTFRM_TEPT5700_1_DEV_ID - Vishay Light Sensor - TEPT5700 (analog)
               https://www.vishay.com/docs/81321/tept5700.pdf
 * 0x11 - 17 - PLTFRM_SFH_7773_1_DEV_ID - Osram Light Sensor SFH 7773 
 *             http://www.datasheetlib.com/datasheet/1363949/sfh-7773_osram-opto-semiconductors.html
 * 0x12 - 18 - PLTFRM_TSL45315_1_DEV_ID - TAOS Digital Ambient Light sensor TSL45315 
 *             http://pdf1.alldatasheet.com/datasheet-pdf/view/454515/TAOS/TSL45315.html
 * 0x13 - 19 - PLTFRM_MPU6050_1_DEV_ID - 6 axis** Gyro + Accelerometer (digital) 
               https://www.invensense.com/wp-content/uploads/2015/02/MPU-6000-Datasheet1.pdf  
 * 0x14 - 20 - PLTFRM_ADXL345_1_DEV_ID - Accelerometer (digital) ADXL345
               http://www.analog.com/media/en/technical-documentation/data-sheets/ADXL345.pdf
 * 0x15 - 21 - PLTFRM_SHT10_1_TEMP_DEV_ID - Humidity and Temperature Sensor (digital) SHT10 
               https://www.sparkfun.com/datasheets/Sensors/SHT1x_datasheet.pdf
 * 0x16 - 22 - PLTFRM_LIS3MDLTR_1_DEV_ID - ST Microelectronics Magnetometer (digital)* LIS3MDLTR 
               http://www.st.com/resource/en/datasheet/lis3mdl.pdf
 * 0x17 - 23 - Dummy
 * 0x18 - 24 - PLTFRM_SHT10_1_RH_DEV_ID - Humidity and Temperature Sensor (digital) SHT10 
               https://www.sparkfun.com/datasheets/Sensors/SHT1x_datasheet.pdf ** 
 * 0x19 - 25 - PLTFRM_CC2520_1_DEV_ID - TI Second generation 2.4 GHz ZigBee RF transceiver CC2520
               http://www.ti.com/lit/gpn/cc2520
 * 0x1a - 26 - PLTFRM_CC1200_1_DEV_ID - CC1200 TI Low Power High Performance RF Transceiver
               http://www.ti.com/lit/gpn/cc1200
 * 0x1b - 27 - PLTFRM_CC1101_1_DEV_ID - CC1101 TI Low-Power Sub-1GHz RF Transceiver
               http://www.ti.com/lit/gpn/cc1101
 * 0x1c - 28 - Dummy
 * 0x1d - 29 - Dummy
 * 0x1e - 30 - Dummy
 * 0x1f - 31 - Dummy
 * 0x20 - 32 - Dummy
 * 0x21 - 33 - PLTFRM_MS5637_1_DEV_ID - TE** Connectivity Altimeter Pressure Sensor MS5637
               http://www.datasheetlib.com/datasheet/1438151/ms5637-02ba03_msi-measurement-specialties-inc.html 
 * 0x22 - 34 - PLTFRM_SHT15_1_DEV_ID - Humidity and Temperature Sensor (digital) SHT15 
               https://www.sparkfun.com/datasheets/Sensors/SHT1x_datasheet.pdf
 * 0x23 - 35 - PLTFRM_SHT15_1_RH_DEV_ID - Humidity and Temperature Sensor (digital) SHT15 
               https://www.sparkfun.com/datasheets/Sensors/SHT1x_datasheet.pdf
 * 0x24 - 36 - PLTFRM_P43_US_1_DEV_ID - **Couldn't find P43 pressure sensor**
 * 0x25 - 37 - Dummy
 * 0x26 - 38 - PLTFRM_MAX_SONAR_1_DEV_ID - ** MAXBotix Sonar : Product number needed**
 * 0x27 - 39 - PLTFRM_MAX_SONAR_2_DEV_ID - ""
 * 0x28 - 40 - PLTFRM_MAX_SONAR_3_DEV_ID - ""
 * 0x29 - 41 - Dummy
 * 0x2a - 42 - Dummy
 * 0x2b - 43 - Dummy
 * 0x2c - 44 - PLTFRM_AS339_1_DIVER_PRESSURE_DEV_ID - ** Specific info required**
 * 0x2d - 45 - PLTFRM_AS339_1_DIVER_TEMPERATURE_DEV_ID - ** "" **
 * 0x2e - 46 - PLTFRM_AS339_1_DIVER_MOD_PRESSURE_DEV_ID - ** "" **
 * 0x2f - 47 - PLTFRM_AS339_1_DIVER_MOD_TEMPERATURE_DEV_ID - ** "" **
 * 0x30 - 48 - PLTFRM_EKMC160111X_1_DEV_ID - Panasonic Passive Infrared Motion Sensor EKMC160111X
               http://wisense.in/datasheets/papirs-ekmc-catalog.pdf

 * 0x31 - 49 - Dummy 
 * 0x32 - 50 - Dummy
 * 0x33 - 51 - Dummy
 * 0x34 - 52 - PLTFRM_PULSE_CNTR_1_DEV_ID - ** Info reqd**
 * 0x35 - 53 - PLTFRM_PULSE_CNTR_2_DEV_ID - ** "" **
 * 0x36 - 54 - Dummy 
 * 0x37 - 55 - Dummy
 * 0x38 - 56 - PLTFRM_GEN_VOLT_MON_DEV_ID - ** Info reqd **
 * 0x39 - 57 - PLTFRM_GEN_CURRENT_MON_DEV_ID - ** "" **
 * 0x3a - 58 - PLTFRM_EXT_VOLTAGE_MON_DEV_ID - ** "" **
 * 0x3b - 59 - Dummy 
 * 0x3c - 60 - Dummy
 * 0x3d - 61 - Dummy
 * 0x3e - 62 - Dummy
 * 0x3f - 63 - Dummy
 * 0x40 - 64 - PLTFRM_LED_1_DEV_ID - LED GPIO**
 * 0x41 - 65 - PLTFRM_LED_2_DEV_ID - LED GPIO **
 * 0x42 - 66 - Dummy 
 * 0x43 - 67 - Dummy
 * 0x44 - 68 - Dummy
 * 0x45 - 69 - Dummy
 * 0x46 - 70 - Dummy
 * 0x47 - 71 - Dummy
 * 0x48 - 72 - PLTFRM_BAR_CODE_SCANNER_1_DEV_ID - BARCODE SCANNER UART **
 * 0x49 - 73 - Dummy
 * 0x4a - 74 - PLTFRM_AUTO_ASSY_TMON_1_DEV_ID - ** Info reqd **
 * 0x4b - 75 - Dummy
 * 0x4c - 76 - Dummy
 * 0x4d - 77 - Dummy
 * 0x4e - 78 - Dummy
 * 0x4f - 79 - Dummy
 * 0x50 - 80 - PLTFRM_REED_SWITCH_1_DEV_ID - REED SWITCH **
 * 0x51 - 81 - PLTFRM_SPST_SWITCH_1_DEV_ID - SPST SWITCH **
 * 0x52 - 82 - PLTFRM_DUAL_FS_LVL_MON_1_DEV_ID - ** iNFO reqd**
 * 0x53 - 83 - Dummy 
 * 0x54 - 84 - PLTFRM_ACS712_1_CURRENT_DEV_ID - Sparkfun Linear Current Sensor ACS712 **
               https://www.sparkfun.com/datasheets/BreakoutBoards/0712.pdf
 * 0x55 - 85 - PLTFRM_ACS712_2_CURRENT_DEV_ID - Sparkfun Linear Current Sensor ACS712 **
               https://www.sparkfun.com/datasheets/BreakoutBoards/0712.pdf 
 * 0x56 - 86 - PLTFRM_ACS712_3_CURRENT_DEV_ID - Sparkfun Linear Current Sensor ACS712 **
               https://www.sparkfun.com/datasheets/BreakoutBoards/0712.pdf
 * 0x57 - 87 - Dummy 
 * 0x58 - 88 - PLTFRM_INA219_1_BV_DEV_ID - TI I2C Out Current/Power Monitor INA219
               http://www.ti.com/lit/gpn/ina219
 * 0x59 - 89 - PLTFRM_INA219_1_SV_DEV_ID - TI I2C Out Current/Power Monitor INA219
               http://www.ti.com/lit/gpn/ina219
 * 0x5a - 90 - Dummy
 * 0x5b - 91 - Dummy
 * 0x5c - 92 - PLTFRM_INA219_3_BV_DEV_ID - TI I2C Out Current/Power Monitor INA219
               http://www.ti.com/lit/gpn/ina219
 * 0x5d - 93 - PLTFRM_INA219_3_SV_DEV_ID - TI I2C Out Current/Power Monitor INA219
               http://www.ti.com/lit/gpn/ina219
 * 0x5e - 94 - Dummy
 * 0x5f - 95 - Dummy
 * 0x60 - 96 - PLTFRM_MP3V5050GP_1_DEV_ID - NXP pressure sensor MP3V5050GP(analog) 
               https://www.nxp.com/docs/en/data-sheet/MP3V5050.pdf
 * 0x61 - 97 - PLTFRM_HE055T01_1_DEV_ID - Electrohms Closed Loop Hall Effect Current Sensor(analog)
               http://www.electrohms.com/?media_dl=47533 
 * 0x62 - 98 - PLTFRM_MP3V5004GP_1_DEV_ID - NXP Presure Sensor MP3V5004GP(analog)
               https://www.nxp.com/part/MP3V5004GP 
 * 0x63 - 99 - PLTFRM_MPXV5010G_1_DEV_ID - NXP On Chip Pressure Sensor MPXV5010G(analog) 
               https://www.nxp.com/docs/en/data-sheet/MPX5010.pdf
 * 0x64 - 100 - PLTFRM_MP3V5010_1_DEV_ID - NXP On Chip Pressure Sensor MP3V5010(analog)
                https://www.nxp.com/docs/en/data-sheet/MP3V5010.pdf
 * 0x65 - 101 - PLTFRM_LLS_1_DEV_ID - ** Info reqd**
 * 0x66 - 102 - Dummy
 * 0x67 - 103 - Dummy
 * 0x68 - 104 - PLTFRM_BATT_1_DEV_ID - ** Info reqd**
 * 0x69 - 105 - PLTFRM_4_20_CURRENT_SENSOR_ID - ** Info reqd**
 * 0x6a - 106 - PLTFRM_SETRA_3100_1_DEV_ID - Setra Industrial OEM Pressure Transducer SETRA3100
                https://www.setra.com/hubfs/Product_Data_Sheets/Model_3100_Data_Sheet.pdf?t=1525445834215
 * 0x6b - 107 - Dummy
 * 0x6c - 108 - Dummy
 * 0x6d - 109 - Dummy
 * 0x6e - 110 - Dummy
 * 0x6f - 111 - Dummy
 * 0x70 - 112 - PLTFRM_AD7797_1_DEV_ID - Analog A/D Converter for Bridge Sensors AD7797
                http://www.analog.com/media/en/technical-documentation/data-sheets/AD7796_7797.pdf
 * 0x71 - 113 - Dummy
 * 0x72 - 114 - Dummy
 * 0x73 - 115 - Dummy
 * 0x74 - 116 - Dummy
 * 0x75 - 117 - Dummy
 * 0x76 - 118 - Dummy
 * 0x77 - 119 - Dummy
 * 0x78 - 120 - PLTFRM_ON_CHIP_VCC_SENSOR_DEV_ID - TI MSP230 on Chip Voltage Sensor
                http://wisense.in/datasheets/msp430g2955.pdf
                
 * 0x79 - 121 - PLTFRM_ON_CHIP_TEMP_SENSOR_DEV_ID - TI MSP230 on Chip Temperature Sensor
                http://wisense.in/datasheets/msp430g2955.pdf
 * 0x7a - 122 - Dummy 
 * 0x7b - 123 - Dummy
 * 0x7c - 124 - Dummy
 * 0x7d - 125 - Dummy
 * 0x7e - 126 - Dummy
 * 0x7f - 127 - Dummy
 * 0x80 - 128 - PLTFRM_SYNC_RT_1_DEV_ID - **Info reqd**
 * 0x81 - 129 - Dummy 
 * 0x82 - 130 - Dummy
 * 0x83 - 131 - Dummy
 * 0x84 - 132 - Dummy
 * 0x85 - 133 - Dummy
 * 0x86 - 134 - Dummy
 * 0x87 - 135 - Dummy
 * 0x88 - 136 - PLTFRM_MAG3110_1_DEV_ID - NXP High Accuracy 3D Magnetometer MAG3110
                https://www.nxp.com/docs/en/data-sheet/MAG3110.pdf
 * 0x89 - 137 - Dummy
 * 0x8a - 138 - Dummy
 * 0x8b - 139 - Dummy
 * 0x8c - 140 - Dummy
 * 0x8d - 141 - Dummy
 * 0x8e - 142 - Dummy
 * 0x8f - 143 - Dummy
 * 0x90 - 144 - PLTFRM_LOGIC_1_DEV_ID - **Info reqd**
 * 0x91 - 145 - PLTFRM_CHIRP_PWLA_1_DEV_ID - **Info reqd**
 * 0x92 - 146 - PLTFRM_FC_28_1_DEV_ID - FC-28 Soil Moisture Sensor **
                http://artofcircuits.com/product/fc-28-soil-moisture-sensor-analog-and-digital-outputs
 * 0x93 - 147 - PLTFRM_WSMS100_1_DEV_ID - **Info reqd**
 * 0x94 - 148 - Dummy
 * 0x95 - 149 - Dummy
 * 0x96 - 150 - Dummy
 * 0x97 - 151 - Dummy
 * 0x98 - 152 - Dummy
 * 0x99 - 153 - Dummy
 * 0x9a - 154 - Dummy
 * 0x9b - 155 - Dummy
 * 0x9c - 156 - Dummy
 * 0x9d - 157 - Dummy
 * 0x9e - 158 - Dummy
 * 0x9f - 159 - Dummy
 * 0xa0 - 160 - PLTFRM_UART_HW_1_DEV_ID - **Info reqd**
 * 0xa1 - 161 - Dummy
 * 0xa2 - 162 - Dummy
 * 0xa3 - 163 - Dummy
 * 0xa4 - 164 - Dummy
 * 0xa5 - 165 - Dummy
 * 0xa6 - 166 - Dummy
 * 0xa7 - 167 - Dummy
 * 0xa8 - 168 - Dummy
 * 0xa9 - 169 - Dummy
 * 0xaa - 170 - Dummy
 * 0xab - 171 - Dummy
 * 0xac - 172 - Dummy
 * 0xad - 173 - Dummy
 * 0xae - 174 - Dummy
 * 0xaf - 175 - Dummy
 * 0xb0 - 176 - PLTFRM_CC2D33S_1_RH_DEV_ID - Humidity Temperature Sensor CC2D33S **
                https://www.mouser.com/datasheet/2/18/AAS-920-558E-Telaire_ChipCap2-021718-web-1315821.pdf
 * 0xb1 - 177 - PLTFRM_CC2D33S_1_TEMP_DEV_ID - Humidity Temperature Sensor CC2D33S **
                https://www.mouser.com/datasheet/2/18/AAS-920-558E-Telaire_ChipCap2-021718-web-1315821.pdf
 * 0xb2 - 178 - Dummy
 * 0xb3 - 179 - Dummy
 * 0xb4 - 180 - Dummy
 * 0xb5 - 181 - Dummy
 * 0xb6 - 182 - Dummy
 * 0xb7 - 183 - Dummy
 * 0xb8 - 184 - PLTFRM_MPL3115A2_1_DEV_ID - NXP I2C Piezoresistive Absolute Pressure Sensor MPL3115A2
                https://www.nxp.com/docs/en/data-sheet/MPL3115A2.pdf
 * 0xb9 - 185 - PLTFRM_MPL115A2_1_DEV_ID - NXP Miniature Absolute Pressure Sensor MPL115A2
                https://www.nxp.com/docs/en/data-sheet/MPL115A2.pdf
 * 0xba - 186 - PLTFRM_BMP180_1_DEV_ID - Bosch Barometric Pressure Sensor BMP180
                https://ae-bst.resource.bosch.com/media/_tech/media/datasheets/BST-BMP180-DS000-12.pdf      
 * 0xbb - 187 - Dummy
 * 0xbc - 188 - Dummy
 * 0xbd - 189 - Dummy
 * 0xbe - 190 - PLTFRM_HPM_1_PM2PT5_DEV_ID - **info reqd** 
 * 0xbf - 191 - PLTFRM_HPM_1_PM10_DEV_ID - **info reqd**
 * 0xc0 - 192 - PLTFRM_MMA7660FC_1_DEV_ID - NXP I2C 3-Axis Accelerometer MMA7660FC
                https://www.nxp.com/docs/en/data-sheet/MMA7660FC.pdf
 * 0xc1 - 193 - Dummy 
 * 0xc2 - 194 - Dummy
 * 0xc3 - 195 - Dummy
 * 0xc4 - 196 - Dummy
 * 0xc5 - 197 - Dummy
 * 0xc6 - 198 - Dummy
 * 0xc7 - 199 - Dummy
 * 0xc8 - 200 - Dummy
 * 0xc9 - 201 - Dummy
 * 0xca - 202 - PLTFRM_MDS_1_DEV_ID **info reqd**
 * 0xcb - 203 - Dummy 
 * 0xcc - 204 - PLTFRM_VIBRATION_SNSR_1_DEV_ID **info reqd**
 * 0xcd - 205 - Dummy 
 * 0xce - 206 - Dummy
 * 0xcf - 207 - Dummy
 * 0xd0 - 208 - Dummy
 * 0xd1 - 209 - Dummy
 * 0xd2 - 210 - Dummy
 * 0xd3 - 211 - Dummy
 * 0xd4 - 212 - Dummy
 * 0xd5 - 213 - Dummy
 * 0xd6 - 214 - Dummy
 * 0xd7 - 215 - Dummy
 * 0xd8 - 216 - Dummy
 * 0xd9 - 217 - Dummy
 * 0xda - 218 - Dummy
 * 0xdb - 219 - Dummy
 * 0xdc - 220 - Dummy
 * 0xdd - 221 - Dummy
 * 0xde - 222 - Dummy
 * 0xdf - 223 - Dummy
 * 0xe0 - 224 - PLTFRM_I2C_SW_BUS_1_DEV_ID ** info req**
 * 0xe1 - 225 - PLTFRM_I2C_SW_BUS_2_DEV_ID **info reqd**
 * 0xe2 - 226 - Dummy
 * 0xe3 - 227 - Dummy
 * 0xe4 - 228 - Dummy
 * 0xe5 - 229 - Dummy
 * 0xe6 - 230 - Dummy
 * 0xe7 - 231 - Dummy
 * 0xe8 - 232 - PLFRM_SPI_HW_BUS_1_DEV_ID **info reqd**
 * 0xe9 - 233 - Dummy
 * 0xea - 234 - PLTFRM_WS_VEH_DET_1_DEV_ID ** info req**
 * 0xeb - 235 - Dummy 
 * 0xec - 236 - Dummy
 * 0xed - 237 - Dummy
 * 0xee - 238 - Dummy
 * 0xef - 239 - Dummy
 * 0xf0 - 240 - PLTFRM_DEV_TYPE_SOLAR_PWR_SRC_VSENSE ** info req**
 * 0xf1 - 241 - PLTFRM_DEV_TYPE_SOLAR_PWR_SRC_ISENSE ** info req**
 * 0xf2 - 242 - PLTFRM_SOL_PSU_1_DEV_ID ** info req**
 * 0xf3 - 243 - PLTFRM_SOL_PSU_1_VBATT_DEV_ID ** info req**
 * 0xf4 - 244 - PLTFRM_SOL_PSU_1_VSYS_DEV_ID ** info req**
 * 0xf5 - 245 - PLTFRM_SOL_PSU_1_ISOL_DEV_ID ** info req**
 * 0xf6 - 246 - PLTFRM_SOL_PSU_1_IBATT_DEV_ID ** info req** 
 * 0xf7 - 247 - Dummy
 * 0xf8 - 248 - Dummy
 * 0xf9 - 249 - Dummy
 * 0xfa - 250 - Dummy
 * 0xfb - 251 - PLTFRM_WPDS_DEV_ID ** info req** 
 * 0xfc - 252 - Dummy
 * 0xfd - 253 - Dummy
 * 0xfe - 254 - PLTFRM_32KHZ_CRYSTAL_DEV_ID ** info req**
 * 0xff - 255 - PLTFRM_GENERIC_DEV_ID ** info req**
*/ 

#define PLTFRM_DUMMY_DEV_ID        0x0

// Serial EEPROM
#define PLTFRM_AT24C01C_1_DEV_ID    0x1           // I2C
#define PLTFRM_AT24C01C_1_I2C_ADDR  0x0  

// Serial EEPROM with EUI-64 and 128 bit serial number
#define PLTFRM_AT24MAC602_DEV_CNT  1
#define PLTFRM_AT24MAC602_1_DEV_ID    0x2
#define PLTFRM_AT24MAC602_1_I2C_ADDR  0x0
   
// Temperature sensors   
#define PLTFRM_LM75B_1_DEV_ID       0x9            // I2C
#define PLTFRM_LM75B_1_I2C_ADDR     0x0
#define PLTFRM_LMP75B_DEV_CNT       0x1            // Number of such devices in the system

#define PLTFRM_TMP102_1_DEV_ID      0xa            // I2C
#define PLTFRM_TMP102_1_I2C_ADDR    0x0            // A0 pin connected to ground
#define PLTFRM_TMP102_DEV_CNT       0x1

// #define PLTFRM_NTC_THERMISTOR_1_DEV_ID   0xb       // Vishay - NTCALUG02A (analog)
// #define PLTFRM_NTC_THERMISTOR_2_DEV_ID   0xc       // Vishay - NTCALUG02A (analog)

#define PLTFRM_NXFT15XH103_1_DEV_ID      0xd       // Murata - NXFT15XH103 (analog)
#define PLTFRM_NTCALUG02A_1_DEV_ID   0xb       // Vishay - NTCALUG02A (analog)
#define PLTFRM_NTCALUG02A_2_DEV_ID   0xc       // Vishay - NTCALUG02A (analog)
#define PLTFRM_NXFT15XH103_2_DEV_ID      0xe   // Murata - NXFT15XH103 (analog)
#define PLTFRM_DNAX300R103L040_1_DEV_ID  0xf   // Deem

#define PLTFRM_TEPT5700_1_DEV_ID   0x10   // Vishay light sensor

// Light sensor
#define PLTFRM_SFH_7773_1_DEV_ID    0x11           // I2C
#define PLTFRM_SFH_7773_1_I2C_ADDR  0x0
#define PLTFRM_SFH_7773_DEV_CNT     0x1            // Number of such devices in the system

// Light sensor
#define PLTFRM_TSL45315_1_DEV_ID    0x12           // I2C
#define PLTFRM_TSL45315_1_I2C_ADDR  0x0
#define PLTFRM_TSL45315_DEV_CNT     0x1            // Number of such devices in the system
   
// Gyro + Accelerometer + Temp
#define PLTFRM_MPU6050_1_DEV_ID     0x13           // I2C
#define PLTFRM_MPU6050_1_I2C_ADDR   0x0            // LSB is 0 (AD0 is 0)
#define PLTFRM_MPU6050_DEV_CNT      0x1            // Number of such devices in the system

// Accelerometer
#define PLTFRM_ADXL345_1_DEV_ID     0x14           // I2C and SPI
#define PLTFRM_ADXL345_DEV_CNT      0x1            // Number of such devices in the system

// SHT-10 (humidity + temperature)
#define PLTFRM_SHT10_1_TEMP_DEV_ID       0x15           // I2C
#define PLTFRM_SHT10_1_RH_DEV_ID       0x18           // I2C
#define PLTFRM_SHT10_DEV_CNT        0x1

// SHT-15 (humidity + temperature)
#define PLTFRM_SHT15_1_DEV_ID          0x22        // I2C
#define PLTFRM_SHT15_1_TEMP_DEV_ID     PLTFRM_SHT15_1_DEV_ID        // I2C
#define PLTFRM_SHT15_1_RH_DEV_ID       0x23        // I2C
#define PLTFRM_SHT15_DEV_CNT           0x1


#define LIS3MDLTR_I2C_ADDR_PREFIX   0x1c           // 0 0011100
// LIS3MDLTR (Magnetometer)
#define PLTFRM_LIS3MDLTR_1_DEV_ID   0x16           // I2C
#define PLTFRM_LIS3MDLTR_1_I2C_ADDR (LIS3MDLTR_I2C_ADDR_PREFIX | 0x0)  // 00111x0 , x is 0
#define PLTFRM_LIS3MDLTR_DEV_CNT    0x1


// RADIO
#define PLTFRM_CC2520_1_DEV_ID      0x19           // SPI
#define PLTFRM_CC1200_1_DEV_ID      0x1a           // SPI
#define PLTFRM_CC1101_1_DEV_ID      0x1b           // SPI

// Pressure sensor
#define PLTFRM_MPL115A1_1_DEV_ID    0x20           // SPI
#define PLTFRM_MS5637_1_DEV_ID      0x21

#define PLTFRM_P43_US_1_DEV_ID  0x24


#define PLTFRM_MAX_SONAR_DEV_CNT    3              // MAXBOTIX ultrasonic
#define PLTFRM_MAX_SONAR_1_DEV_ID   0x26
#define PLTFRM_MAX_SONAR_2_DEV_ID   0x27
#define PLTFRM_MAX_SONAR_3_DEV_ID   0x28

#define PLTFRM_AS339_1_DIVER_PRESSURE_DEV_ID  0x2c //
#define PLTFRM_AS339_1_DIVER_TEMPERATURE_DEV_ID  0x2d
#define PLTFRM_AS339_1_DIVER_MOD_PRESSURE_DEV_ID  0x2e
#define PLTFRM_AS339_1_DIVER_MOD_TEMPERATURE_DEV_ID  0x2f

#define PLTFRM_EKMC160111X_1_DEV_ID   0x30         // GPIO Panasonic PIR
#define PLTFRM_EKMC160111X_DEV_CNT    0x1          // Number of such devices in the system

#define PLTFRM_PULSE_CNTR_1_DEV_ID  0x34
#define PLTFRM_PULSE_CNTR_2_DEV_ID  0x35

#define PLTFRM_GEN_VOLT_MON_DEV_ID   0x38 
#define PLTFRM_GEN_CURRENT_MON_DEV_ID   0x39 

#define PLTFRM_EXT_VOLTAGE_MON_DEV_ID   0x3a

// LEDs
#define PLTFRM_LED_1_DEV_ID           0x40         // GPIO
#define PLTFRM_LED_2_DEV_ID           0x41         // GPIO

#define PLTFRM_BAR_CODE_SCANNER_1_DEV_ID   0x48    // UART

#define PLTFRM_AUTO_ASSY_TMON_1_DEV_ID  0x4a

// Switches (On/Off)
#define PLTFRM_REED_SWITCH_1_DEV_ID   0x50         // GPIO
#define PLTFRM_REED_SWITCH_DEV_CNT    0x1

#define PLTFRM_SPST_SWITCH_1_DEV_ID   0x51         // GPIO
#define PLTFRM_SPST_SWITCH_DEV_CNT    0x1

#define PLTFRM_DUAL_FS_LVL_MON_1_DEV_ID  0x52  

#define PLTFRM_ACS712_1_CURRENT_DEV_ID   0x54      // Analog
#define PLTFRM_ACS712_2_CURRENT_DEV_ID   0x55      // Analog
#define PLTFRM_ACS712_3_CURRENT_DEV_ID   0x56      // Analog
#define PLTFRM_ACS712_DEV_CNT  3


// Analog Pressure Sensor
#define PLTFRM_MP3V5050GP_1_DEV_ID    0x60         // Analog input
#define PLTFRM_MP3V5050GP_DEV_CNT     0x1

#define PLTFRM_HE055T01_1_DEV_ID      0x61         // Analog input
#define PLTFRM_HE055T01_DEV_CNT       0x1

#define PLTFRM_MP3V5004GP_1_DEV_ID    0x62         // Analog input
#define PLTFRM_MP3V5004GP_DEV_CNT     0x1

#define PLTFRM_MPXV5010G_1_DEV_ID    0x63         // Analog input
#define PLTFRM_MPXV5010G_DEV_CNT     0x1

#define PLTFRM_MP3V5010_1_DEV_ID      0x64
#define PLTFRM_MP3V5010_DEV_CNT       1

#define PLTFRM_LLS_1_DEV_ID           0x65

#define PLTFRM_BATT_1_DEV_ID          0x68         // Analog input
#define PLTFRM_BATT_DEV_CNT           0x1

#define PLTFRM_4_20_CURRENT_SENSOR_ID    0x69       // Analog input
#define PLTFRM_4_20_CURRENT_SENSOR_CNT   0x1

#define PLTFRM_SETRA_3100_1_DEV_ID    0x6a
#define PLTFRM_SETRA_3100_DEV_CNT   1

// AD7797 (Bridge sensor)
#define PLTFRM_AD7797_1_DEV_ID        0x70
#define PLTFRM_AD7797_DEV_CNT         0x1          // SPI bus


// MSP430 Voltage reading
#define PLTFRM_ON_CHIP_VCC_SENSOR_DEV_ID    0x78      // ADC_10 channel
#define PLTFRM_ON_CHIP_VCC_SENSOR_DEV_CNT   0x1

// MSP430 Voltage reading 
#define PLTFRM_ON_CHIP_TEMP_SENSOR_DEV_ID    0x79      // ADC_10 channel
#define PLTFRM_ON_CHIP_TEMP_SENSOR_DEV_CNT   0x1


#define PLTFRM_SYNC_RT_1_DEV_ID  0x80
#define PLTFRM_SYNC_RT_DEV_CNT  0x1

#define PLTFRM_MAG3110_1_DEV_ID  0x88

#define PLTFRM_INA219_1_BV_DEV_ID     0x58         // I2C   INA219 bus voltage
#define PLTFRM_INA219_1_SV_DEV_ID     0x59         // I2C   INA219 shunt voltage
#define PLTFRM_INA219_DEV_CNT         0x1

#define PLTFRM_INA219_3_BV_DEV_ID     0x5c         // I2C   INA219 bus voltage
#define PLTFRM_INA219_3_SV_DEV_ID     0x5d         // I2C   INA219 shunt voltage

#define PLTFRM_GPIO_LOGIC_SZ  0x1
#define PLTFRM_LOGIC_1_DEV_ID  0x90
// #define PLTFRM_LOGIC_2_DEV_ID  0x91

#define PLTFRM_CHIRP_PWLA_1_DEV_ID  0x91
#define PLTFRM_CHIRP_PWLA_DEV_CNT 1

#define PLTFRM_FC_28_1_DEV_ID  0x92
#define PLTFRM_FC_28_DEV_CNT  1

#define PLTFRM_WSMS100_1_DEV_ID  0x93

#define PLTFRM_CC2D33S_1_RH_DEV_ID      0xb0  // I2C
#define PLTFRM_CC2D33S_1_TEMP_DEV_ID    0xb1  // I2C

#define PLTFRM_MPL3115A2_1_DEV_ID  0xb8  // I2C
#define PLTFRM_MPL3115A2_DEV_CNT   0x1

#define PLTFRM_MPL115A2_1_DEV_ID  0xb9  // I2C
#define PLTFRM_MPL115A2_DEV_CNT  0x1

#define PLTFRM_BMP180_1_DEV_ID  0xba  // I2C
#define PLTFRM_BMP180_DEV_CNT  0x1

#define PLTFRM_HPM_1_PM2PT5_DEV_ID  0xbe
#define PLTFRM_HPM_1_PM10_DEV_ID  0xbf

#define PLTFRM_MMA7660FC_1_DEV_ID  0xc0  // I2C
#define PLTFRM_MMA7660FC_DEV_CNT   0x1

#define PLTFRM_MDS_1_DEV_ID  0xca

#define PLTFRM_VIBRATION_SNSR_1_DEV_ID  0xcc

#define PLTFRM_I2C_SW_BUS_1_DEV_ID  0xe0
#define PLTFRM_I2C_SW_BUS_2_DEV_ID  0xe1

#define PLFRM_SPI_HW_BUS_1_DEV_ID   0xe8

#define PLTFRM_WS_VEH_DET_1_DEV_ID  0xea

#define PLTFRM_DEV_TYPE_SOLAR_PWR_SRC_VSENSE  0xf0
#define PLTFRM_DEV_TYPE_SOLAR_PWR_SRC_ISENSE  0xf1

#define PLTFRM_SOL_PSU_1_DEV_ID  0xf2
#define PLTFRM_SOL_PSU_1_VSOL_DEV_ID  0xf2
#define PLTFRM_SOL_PSU_1_VBATT_DEV_ID  0xf3
#define PLTFRM_SOL_PSU_1_VSYS_DEV_ID  0xf4
#define PLTFRM_SOL_PSU_1_ISOL_DEV_ID  0xf5
#define PLTFRM_SOL_PSU_1_IBATT_DEV_ID  0xf6

#define PLTFRM_WPDS_DEV_ID  0xfb
#define PLTFRM_32KHZ_CRYSTAL_DEV_ID  0xfe

#define PLTFRM_GENERIC_DEV_ID      0xff

// --------------------------------------------------------- 
   
   
// ------------- Buses (I2C, SPI, 1-WIRE etc) --------------   
// I2C (software)
#define PLTFRM_I2C_SW_BUS_1_ID      0x80

   
// I2C (hardware) 
#define PLFRM_I2C_HW_BUS_1_ID      0x88

#define PLTFRM_INV_I2C_BUS_ID      0xff
#define PLTFRM_INV_I2C_ADDR        0xff
 
// SPI (hardware)
#define PLFRM_SPI_HW_BUS_1_ID      0x90

// 1 WIRE (software)
#define PLTFRM_1WIRE_SW_BUS_1_ID   0x98
   
// UART
#define PLTFRM_UART_HW_1_DEV_ID    0xa0
// ---------------------------------------------------------   


#define NTC_THERM_103AT_4_R25_VAL  10000
#define NTC_THERM_103AT_4_B_25_85_VAL   3435

#define NTC_THERM_NTCALUG02A_R25_VAL  10000
#define NTC_THERM_NTCALUG02A_B_25_85_VAL   3984


#define NTC_THERM_NXFT15XH103_R25_VAL  10000
#define NTC_THERM_NXFT15XH103_B_25_85_VAL   3380

#define NTC_THERM_DNAX300R103L040_4_R25_VAL  10000
#define NTC_THERM_DNAX300R103L040_4_B_25_85_VAL  3950

// ---------------------------------------------------------

typedef enum
{
   PLTFRM_GPIO_PORT_1 = 0,
   PLTFRM_GPIO_PORT_2 = 1,
   PLTFRM_GPIO_PORT_3 = 2,
   PLTFRM_GPIO_PORT_4 = 3,

#ifdef __MSP430F5419A__
   PLTFRM_GPIO_PORT_5 = 4,
   PLTFRM_GPIO_PORT_6 = 5,
   PLTFRM_GPIO_PORT_7 = 6,
   PLTFRM_GPIO_PORT_8 = 7,
   PLTFRM_GPIO_PORT_9 = 8,
   PLTFRM_GPIO_PORT_10 = 9,
   PLTFRM_GPIO_PORT_11 = 10
#endif

} PLTFRM_gpioPortId_t;


typedef enum
{
   PLTFRM_GPIO_PORT_PIN_0,
   PLTFRM_GPIO_PORT_PIN_1,
   PLTFRM_GPIO_PORT_PIN_2,
   PLTFRM_GPIO_PORT_PIN_3,
   PLTFRM_GPIO_PORT_PIN_4,
   PLTFRM_GPIO_PORT_PIN_5,
   PLTFRM_GPIO_PORT_PIN_6,
   PLTFRM_GPIO_PORT_PIN_7
} PLTFRM_gpioPortPin_t;

#endif
```
