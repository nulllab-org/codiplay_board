# Codiplay Board

## 主控

Codiplay Board是使用ESP32-WROOM-32模组作为主控，ESP32-WROOM-32是一款通用型Wi-Fi+Bluetooth® + Bluetooth LE MCU模组，功能强大，用途广泛，可以用于低功耗传感器网络和要求极高的任务，例如语音编码、音频流和MP3解码等。

此款模组的核心是ESP32-D0WDQ6芯片，具有可扩展、自适应的特点。两个CPU核可以被单独控制。时钟频率的调节范围为80MHz到240MHz。用户可以切断CPU的电源，利用低功耗协处理器来不断地监测外设的状态变化或某些模拟量是否超出阈值。ESP32还集成了丰富的外设，包括电容式触摸传感器、低噪声传感放大器，SD卡接口、以太网接口、高速SDIO/SPI、UART、I2S和I2C等。

模组集成了传统蓝牙、低功耗蓝牙和Wi-Fi，具有广泛的用途：Wi-Fi支持极大范围的通信连接，也支持通过路由器直接连接互联网；而蓝牙可以让用户连接手机或者广播Bluetooth LE Beacon以便于信号检测。ESP32芯片的睡眠电流小于5µA，使其适用于电池供电的可穿戴电子设备。模组支持的数据传输速率高达150Mbps，天线输出功率达到20dBm，可实现最大范围的无线通信。因此，这款模组具有行业领先的技术规格，在高集成度、无线传输距离、功耗以及网络联通等方面性能极佳。

### 特性

#### MCU

ESP32-D0WDQ6内置两个低功耗Xtensa® 32-bit LX6 MCU

- Xtensa® 32-bit LX6单/双核处理器

- CoreMark® 得分：

  - 单核，主频240MHz：504.85CoreMark；2.10 CoreMark/MHz

  - 双核，主频240MHz：994.26CoreMark；4.14 CoreMark/MHz

#### 存储

- 448KB的ROM，用于程序启动和内核功能调用

- 520KB的片上SRM，用于数据和指令存储

- 模组集成了4MB的SPI flash，连接ESP32的管脚GPIO6，GPIO7，GPIO8，GPIO9，GPIO10和GPIO11。

#### 晶振

模组使用40MHz晶振。

#### Wi-Fi

- 支持IEEE802.11b/g/n 协议

- 802.11n (2.4 GHz) 速度高达 150 Mbps

- 无线多媒体(WMM)

- 帧聚合(TX/RXA-MPDU, RX A-MSDU)

- 立即块确认(ImmediateBlock ACK)

- 重组(Defragmentation)

- Beacon 自动监测（硬件TSF）

- 4个虚拟Wi-Fi接口

- 同时支持基础结构型网络(InfrastructureBSS) Station 模式/SoftAP 模式/混杂模式

- 天线分集

#### 蓝牙

- 蓝牙v4.2完整标准，包含传统蓝牙(BR/EDR)和低功耗蓝牙(BluetoothLE)

- 支持标准Class-1、Class-2 和 Class-3，且无需外部功率放大器

- 增强型功率控制(EnhancedPowerControl)

- 输出功率高达+9dBm

- NZIF 接收器具有–94dBm的BLE接收灵敏度

- 自适应跳频(AFH)

- 基于SDIO/SPI/UART 接口的标准HCI

- 高速UARTHCI，最高可达4Mbps

- 支持蓝牙4.2BR/EDR和Bluetooth LE 双模controller

- 同步面向连接/扩展同步面向连接(SCO/eSCO)

- CVSD和SBC音频编解码算法

- 蓝牙微微网(Piconet)和散射网(Scatternet)

- 支持传统蓝牙和低功耗蓝牙的多设备连接

- 支持同时广播和扫描

#### 时钟和定时器

- 内置8MHz振荡器，支持自校准

- 内置RC振荡器，支持自校准

- 支持外置2MHz至60MHz的主晶振（如果使用Wi-Fi/蓝牙功能，则目前仅支持40MHz晶振）

- 支持外置32kHz晶振，用于RTC，支持自校准

- 2个定时器群组，每组包括2个64-bit通用定时器和1个主系统看门狗

- 1 个RTC定时器

- RTC看门狗

#### 高级外设接口

- 34个GPIO口

  - 5个作为strapping管脚

  - 6个仅为输入管脚

  - 6个用于连接封装内flash/PSRAM

- 12-bit SAR ADC，多达 18 个通道

- 2个8-bit D/A 转换器

- 10 个触摸传感器

- 4个SPI

- 2个I2S

- 2个I2C

- 3个UART

- 1个HostSD/eMMC/SDIO

- 1个Slave SDIO/SPI

- 带有专用DMA的以太网MAC接口，支持IEEE1588

- TWAI®，兼容ISO11898-1（CAN 规范 2.0）

- RMT(TX/RX)

- 电机PWM

- LED PWM，多达16个通道

## 板载资源

主板将ESP32模组中的23个GPIO口引出作为用户的可操作的IO口，并组成PH2.0端口用于接入各种类型的传感器。

| GPIO | 功能 | 端口 |
| --- | --- | --- |
| GPIO2 | 数字输入、输出、ADC | 板载LED灯，使用特定固件时用户无法操作，用于蓝牙连接指示灯 |
| GPIO4 | 数字输入、数字输出、ADC、PWM | P2 [4 3V3 G] |
| GPIO5 | 数字输入、数字输出、ADC、PWM | P1 [5 3V3 G] |
| GPIO12 | 数字输入、数字输出、ADC | P10 [12 13 5V G] |
| GPIO13 | 数字输入、数字输出、ADC | P10 [12 13 5V G] |
| GPIO14 | 数字输入、数字输出、ADC | P9 [14 15 5V G]</br>P15 [14 15 16 17 5V G] |
| GPIO15 | 数字输入、数字输出、ADC | P9 [14 15 5V G]</br>P15 [14 15 16 17 5V G] |
| GPIO16 | 数字输入、数字输出 | P15 [14 15 16 17 5V G] |
| GPIO17 | 数字输入、数字输出 | P15 [14 15 16 17 5V G] |
| GPIO18 | 数字输入、数字输出 | P11 [18 36 3V3 G] |
| GPIO19 | 数字输入、数字输出 | P12 [19 39 3V3 G] |
| GPIO21 | 数字输入、数字输出、I2C SDA | I2C [SCL SDA 5V G] |
| GPIO22 | 数字输入、数字输出、I2C SCL | I2C [SCL SDA 5V G] |
| GPIO23 | 数字输入、数字输出 | P14 [23 32 33 3V3 G] |
| GPIO25 | 数字输入、数字输出、ADC、PWM | P7 [25 3V3 G] </br> P13 [25 26 27 3V3 G]|
| GPIO26 | 数字输入、数字输出、ADC、PWM | P8 [26 3V3 G] </br> P13 [25 26 27 3V3 G]|
| GPIO27 | 数字输入、数字输出、ADC | P13 [25 26 27 3V3 G] |
| GPIO32 | 数字输入、数字输出、ADC | P14 [23 32 33 3V3 G] |
| GPIO33 | 数字输入、数字输出、ADC | P14 [23 32 33 3V3 G] |
| GPIO34 | 数字输入、数字输出、ADC | P6 [34 3V3 G] |
| GPIO35 | 数字输入、数字输出、ADC | P5 [35 3V3 G] |
| GPIO36 | 数字输入、数字输出、ADC | P4 [36 3V3 G] </br> P11 [18 36 3V3 G] |
| GPIO39 | 数字输入、数字输出、ADC | P3 [39 3V3 G] </br> P12 [19 39 3V3 G] |

## 供电

DC Power jack 2.1x5.5mm，支持6V-12V供电输入

## 连接

Type C Connector
