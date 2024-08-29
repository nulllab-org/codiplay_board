# Codiplay Board

## Description

## Main Control

The Codiplay Board uses the ESP32-WROOM-32 module as the main control. The ESP32-WROOM-32 is a general-purpose Wi-Fi + Bluetooth® + Bluetooth LE MCU module, which is powerful and has a wide range of uses. It can be used in low-power sensor networks and extremely demanding tasks, such as voice coding, audio streaming, and MP3 decoding.

The core of this module is the ESP32-D0WDQ6 chip, which is scalable and adaptive. The two CPU cores can be controlled separately. The clock frequency can be adjusted from 80MHz to 240MHz. Users can cut off the power supply of the CPU and use the low-power coprocessor to continuously monitor the state changes of the peripherals or whether certain analog quantities exceed the threshold. ESP32 also integrates a rich set of peripherals, including capacitive touch sensors, low-noise sensing amplifiers, SD card interfaces, Ethernet interfaces, high-speed SDIO/SPI, UART, I2S, and I2C.

The module integrates traditional Bluetooth, low-power Bluetooth, and Wi-Fi, and has a wide range of uses: Wi-Fi supports a wide range of communication connections and also supports direct connection to the Internet through a router; while Bluetooth allows users to connect to mobile phones or broadcast Bluetooth LE Beacon for signal detection. The sleep current of the ESP32 chip is less than 5µA, making it suitable for battery-powered wearable electronic devices. The module supports a data transmission rate of up to 150Mbps, and the antenna output power reaches 20dBm, which can achieve the maximum range of wireless communication. Therefore, this module has industry-leading technical specifications and excellent performance in terms of high integration, wireless transmission distance, power consumption, and network connectivity.

## Features

### MCU

The ESP32-D0WDQ6 has two built-in low-power Xtensa® 32-bit LX6 MCUs

- Xtensa® 32-bit LX6 single/dual-core processor

- CoreMark® score:

  - Single-core, main frequency 240MHz: 504.85 CoreMark; 2.10 CoreMark/MHz
  
  - Dual-core, main frequency 240MHz: 994.26 CoreMark; 4.14 CoreMark/MHz

### Storage

- 448KB of ROM for program startup and kernel function calls

- 520KB of on-chip SRM for data and instruction storage

- The module integrates 4MB of SPI flash, connected to the pins GPIO6, GPIO7, GPIO8, GPIO9, GPIO10, and GPIO11 of ESP32.

### Crystal Oscillator

The module uses a 40MHz crystal oscillator.

### Wi-Fi

- Supports the IEEE802.11b/g/n protocol
- 802.11n (2.4 GHz) speed up to 150 Mbps
- Wireless Multimedia (WMM)
- Frame Aggregation (TX/RXA-MPDU, RX A-MSDU)
- Immediate Block ACK
- Defragmentation
- Beacon Automatic Monitoring (Hardware TSF)
- 4 virtual Wi-Fi interfaces
- Simultaneously supports Infrastructure BSS Station mode/SoftAP mode/Blended mode
- Antenna Diversity

### Bluetooth

- Bluetooth v4.2 complete standard, including traditional Bluetooth (BR/EDR) and low-power Bluetooth (Bluetooth LE)
- Supports standard Class-1, Class-2, and Class-3, and does not require an external power amplifier
- Enhanced Power Control
- Output power up to +9dBm
- NZIF receiver has a BLE receiving sensitivity of -94dBm
- Adaptive Frequency Hopping (AFH)
- Standard HCI based on SDIO/SPI/UART interface
- High-speed UART HCI, up to 4Mbps
- Supports Bluetooth 4.2 BR/EDR and Bluetooth LE dual-mode controller
- Synchronous Connection-Oriented/Extended Synchronous Connection-Oriented (SCO/eSCO)
- CVSD and SBC audio coding and decoding algorithms
- Bluetooth Piconet and Scatternet
- Supports multi-device connection of traditional Bluetooth and low-power Bluetooth
- Supports simultaneous broadcasting and scanning

### Clock and Timer

- Built-in 8MHz oscillator, supports self-calibration
- Built-in RC oscillator, supports self-calibration
- Supports an external main crystal oscillator from 2MHz to 60MHz (if using Wi-Fi/Bluetooth functions, currently only 40MHz crystal oscillator is supported)
- Supports an external 32kHz crystal oscillator for RTC, supports self-calibration
- 2 timer groups, each including 2 64-bit general-purpose timers and 1 main system watchdog
- 1 RTC timer
- RTC watchdog

### Advanced Peripheral Interface

- 34 GPIO ports
  - 5 as strapping pins
  - 6 as input-only pins
  - 6 for connecting the on-chip flash/PSRAM
- 12-bit SAR ADC, up to 18 channels
- 2 8-bit D/A converters
- 10 touch sensors
- 4 SPI
- 2 I2S
- 2 I2C
- 3 UART
- 1 Host SD/eMMC/SDIO
- 1 Slave SDIO/SPI
- Ethernet MAC interface with dedicated DMA, supports IEEE1588
- TWAI®, compatible with ISO11898-1 (CAN specification 2.0)
- RMT (TX/RX)
- Motor PWM
- LED PWM, up to 16 channels

## On-board Resources

The main board leads out 23 GPIO ports in the ESP32 module as user-operable IO ports and forms PH2.0 ports for accessing various types of sensors.

| GPIO | Function | Port |
| --- | --- | --- |
| GPIO2 | Digital Input, Digital Output, ADC | On-board LED, not operable by the user when using a specific firmware, used as a Bluetooth connection indicator |
| GPIO4 | Digital Input, Digital Output, ADC, PWM | P2 [4 3V3 G] |
| GPIO5 | Digital Input, Digital Output, ADC, PWM | P1 [5 3V3 G] |
| GPIO12 | Digital Input, Digital Output, ADC | P10 [12 13 5V G] |
| GPIO13 | Digital Input, Digital Output, ADC | P10 [12 13 5V G] |
| GPIO14 | Digital Input, Digital Output, ADC | P9 [14 15 5V G]</br>P15 [14 15 16 17 5V G] |
| GPIO15 | Digital Input, Digital Output, ADC | P9 [14 15 5V G]</br>P15 [14 15 16 17 5V G] |
| GPIO16 | Digital Input, Digital Output | P15 [14 15 16 17 5V G] |
| GPIO17 | Digital Input, Digital Output | P15 [14 15 16 17 5V G] |
| GPIO18 | Digital Input, Digital Output | P11 [18 36 3V3 G] |
| GPIO19 | Digital Input, Digital Output | P12 [19 39 3V3 G] |
| GPIO21 | Digital Input, Digital Output, I2C SDA | I2C [SCL SDA 5V G] |
| GPIO22 | Digital Input, Digital Output, I2C SCL | I2C [SCL SDA 5V G] |
| GPIO23 | Digital Input, Digital Output | P14 [23 32 33 3V3 G] |
| GPIO25 | Digital Input, Digital Output, ADC, PWM | P7 [25 3V3 G] </br> P13 [25 26 27 3V3 G]|
| GPIO26 | Digital Input, Digital Output, ADC, PWM | P8 [26 3V3 G] </br> P13 [25 26 27 3V3 G]|
| GPIO27 | Digital Input, Digital Output, ADC | P13 [25 26 27 3V3 G] |
| GPIO32 | Digital Input, Digital Output, ADC | P14 [23 32 33 3V3 G] |
| GPIO33 | Digital Input, Digital Output, ADC | P14 [23 32 33 3V3 G] |
| GPIO34 | Digital Input, Digital Output, ADC | P6 [34 3V3 G] |
| GPIO35 | Digital Input, Digital Output, ADC | P5 [35 3V3 G] |
| GPIO36 | Digital Input, Digital Output, ADC | P4 [36 3V3 G] </br> P11 [18 36 3V3 G] |
| GPIO39 | Digital Input, Digital Output, ADC | P3 [39 3V3 G] </br> P12 [19 39 3V3 G] |

## Power Supply

DC Power jack 2.1x5.5mm, supports 6V - 12V power input

## Connector

Type C Connector
