
## © Copyright Chirac Alexandru-Stefan 333CA


# Hardware Overview and Component Specifications

This document outlines the key hardware components used in the system, including their roles and detailed specifications.

---

## 📑 Table of Contents

- [Main Controller](#-main-controller)
- [Display System](#-display-system)
- [Power](#-power-management)
- [Memory and Storage](#-memory-and-storage)
- [Sensors](#-sensors-and-timing)
- [Connectivity](#-connectivity)
- [Block diagram](#block-diagram)
- [Pin Assignments](#pin-assignments)

---

## Main Controller

### ESP32-C6-WROOM-1-N8
- **Function**: Core microcontroller that manages all system operations.

---

## Display System

### E-Paper Display
- **Drive Circuit**: Custom electronics for controlling the display.
- **Display Type Selector**: Configurable support for different e-paper types.

---

## Power

### LDO Voltage Regulator — XC6220A331MR-G
- **Function**: Supplies regulated 3.3V to the system.
- **Input Voltage**: Up to 6.0 V
- **Output Current**: Up to 700 mA

### Battery Charger — MCP73831
- **Function**: Manages Li-Po battery charging.
- **Charge Current**: Up to 500 mA (programmable)
- **Charge Voltage**: Fixed at 4.2 V
- **Input Voltage**: Typically 5 V (USB)
- **Features**: Thermal protection, automatic termination, LED status indicator

### Battery Fuel Gauge — MAX17048G+T10
- **Function**: Monitors battery state-of-charge and voltage.
- **Interface**: I2C
- **Voltage Accuracy**: ±7.5 mV
- **Current Consumption**: ~23 µA

### Supercapacitor — CPH3225A
- **Function**: Provides short-term backup power during power loss.

### Diode — MBR0530
- **Function**: Reverse voltage protection and efficient switching.
- **Max Current**: 0.5 A
- **Forward Voltage**: ~0.3–0.4 V

---

## Memory and Storage

### External NOR Flash — W25Q512JVEIQ
- **Function**: High-capacity external storage.
- **Capacity**: 512 Mbit (64 MB)
- **Interface**: SPI
- **Voltage**: 3.3 V
- **Usage**: Firmware, configuration data, graphical assets

### SD Card Slot
- **Function**: Expandable storage option for user or application data.

---

## Sensors

### Environmental Sensor — BME688
- **Function**: Measures environmental data.
- **Measurements**: Temperature, Humidity, Pressure, VOC gas
- **Interface**: I2C
- **Operating Voltage**: 1.7 V – 3.6 V

### RTC Module — DS3231SN
- **Function**: Maintains accurate timekeeping.
- **Accuracy**: ±2 ppm (~1 minute/year)
- **Interface**: I2C
- **Voltage**: 2.3 V – 5.5 V
- **Feature**: Integrated battery backup

---

## Connectivity

### USB-C Connector
- **Function**: Provides both power input and data communication.

### ESD Protection — USBLC6-2SC6Y
- **Function**: Protects USB lines from electrostatic discharge.

### Qwiic/Stemma QT Connector
- **Function**: Supports I2C-based expansion modules.

---

## Block Diagram

![Block Diagram](Images/Diagrama%20Bloc.png)

---

## Pin Assignments

| ESP32-C6 Pin | Function       | Connected To               | Description                           |
|--------------|----------------|----------------------------|---------------------------------------|
| 3            | RESET          | Reset Button               | System hardware reset                 |
| 4            | SS_SD          | SD Card (pin 2)            | SPI Slave Select for SD card          |
| 6            | SCK            | SD Card (pin 5)            | SPI Clock signal                      |
| 7            | MOSI           | SD Card (pin 3)            | SPI Master Out Slave In               |
| 8            | INT_RTC        | RTC Module (pin 3)         | Interrupt signal from RTC             |
| 9            | 32KHz          | RTC Module (pin 1)         | 32KHz clock signal from RTC           |
| 13           | USB_D-         | USB-C Connector (pin 3)    | USB Data Negative line                |
| 14           | USB_D+         | USB-C Connector (pin 1)    | USB Data Positive line                |
| 15           | IO/BOOT        | Boot Button                | Boot mode selector button             |
| 16           | RTC_RST        | RTC Module (pin 4)         | RTC reset control                     |
| 17           | I2C_PW         | BME688 Sensor (pins 6, 8, 2)| Power control for environmental sensor|
| 19           | SDA            | Multiple I²C devices       | I²C Serial Data line (shared)         |
| 20           | SCL            | Multiple I²C devices       | I²C Serial Clock line (shared)        |
| 23           | IO/CHANGE      | Change Button              | Display/Mode change button            |
| 27           | MISO           | SD Card (pin 7)            | SPI Master In Slave Out               |

---

## Bill of Materials

 | Device | Qty | PURCHASE-URL |
 |--------|-----|--------------|
 | ADAFRUIT_LEDCHIP-LED0603 | 1 | https://www.snapeda.com/parts/KP-1608SURCK/Kingbright/view-part/?ref=search&t=LED%200603 | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | RCL_CPOL-EUCT3528 | 1 | https://a360.co/4iZy6AA | 
 | SJ | 1 | https://grabcad.com/library/solder-jumpers-1 | 
 | VARISTOR_3216 | 1 | https://www.mouser.co.uk/ProductDetail/EPCOS-TDK/B72520T0350K062?qs=dEfas%2FXlABIszF52uu7vrg%3D%3D | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 1 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 1 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 7 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 16 | https://componentsearchengine.com/part-view/R0402%201%%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | 112A-TAAR-R03_ATTEND | 1 | https://store.comet.srl.ro/Catalogue/Product/43497/ | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 1 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 8 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 1 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 1 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | ESP32_WROVER_SPARKFUN-DISCRETESEMI_MOSFET_PCH-DMG2305UX-7 | 2 | https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 1 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 3 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | EAGLE-LTSPICE_CC0402 | 1 | https://componentsearchengine.com/part-view/CC0402MRX5R5BB106/YAGEO | 
 | ESP32_WROVER_EAGLE-LTSPICE_RR0402 | 2 | https://componentsearchengine.com/part-view/R0402%201%25%20100%20K%20(RC0402FR-07100KL)/YAGEO | 
 | 744043680IND_4828-WE-TPC_WRE | 1 | https://eu.mouser.com/ProductDetail/Wurth-Elektronik/744043680?qs=PGXP4M47uW6VkZq%252BkzjrHA%3D%3D | 
 | BD5229G-TR | 1 | https://componentsearchengine.com/part-view/BD5229G-TR/ROHM%20Semiconductor | 
 | BUTTON_CUSYOMV1PACKAGE | 3 | https://www.snapeda.com/parts/EVQP7L01P/Panasonic/view-part/?ref=search&t=evqp7l | 
 | CPH3225A | 1 | https://www.snapeda.com/api/url_track_click_mouser/?unipart_id=562593&manufacturer=Seiko Instruments&part_name=CPH3225A&search_term=None | 
 | DS3231SN# | 1 | https://www.snapeda.com/api/url_track_click_mouser/?unipart_id=99048&manufacturer=Analog Devices&part_name=DS3231SN#&search_term=None | 
 | ESP32-C6-WROOM-1-N8 | 1 | https://www.snapeda.com/parts/ESP32-C6-WROOM-1-N8/Espressif+Systems/view-part/?ref=eda | 
 | ESP32_WROVER_AVX---SD0805S020S1R0_AVX_ SD0805S020S1R0_0_0AVX_SD0805S020S1R0_0_0 | 2 | https://eu.mouser.com/ProductDetail/KYOCERA-AVX/SD0805S020S1R0?qs=jCA%252BPfw4LHbpkAoSnwrdjw%3D%3D | 
 | ESP32_WROVER_BME680_BME680 | 1 | https://www.snapeda.com/parts/BME680/Bosch/view-part/?welcome=home | 
 | ESP32_WROVER_SPARKFUN-IC-POWER_MCP73831 | 1 | https://www.digikey.ro/en/products/detail/microchip-technology/MCP73831T-2ACI-OT/964301 | 
 | FH34SRJ-24S-0.5SH_99_ | 1 | https://componentsearchengine.com/part-view/XC6220A331MR-G/Torex | 
 | MAX17048G+T10 | 1 | https://www.snapeda.com/api/url_track_click_mouser/?unipart_id=329239&manufacturer=Analog%20Devices&part_name=MAX17048G+T10&search_term=None | 
 | MBR0530 | 3 | https://www.snapeda.com/api/url_track_click_mouser/?unipart_id=179458&manufacturer=ON%20Semiconductor&part_name=MBR0530&search_term=None | 
 | PGB1010603MR | 6 | https://www.snapeda.com/api/url_track_click_mouser/?unipart_id=5659453&manufacturer=Littelfuse%20Inc.&part_name=PGB1010603MR&search_term=None | 
 | QWIIC_CONNECTORJS-1MM | 1 | https://www.digikey.ro/en/models/926710 | 
 | SAMACSYS_PARTS_USB4110-GF-A | 1 | https://componentsearchengine.com/part-view/USB4110-GF-A/GCT%20(GLOBAL%20CONNECTOR%20TECHNOLOGY) | 
 | SI1308EDL-T1-GE3 | 1 | https://componentsearchengine.com/part-view/SI1308EDL-T1-GE3/Vishay | 
 | TPTP20R | 17 | https://grabcad.com/library/test-points-printed-circuit-board-1 | 
 | USBLC6-2SC6Y | 1 | https://www.snapeda.com/parts/USBLC6-2SC6Y/STMicroelectronics/view-part/?ref=eda | 
 | W25Q512JVEIQ | 1 | https://www.snapeda.com/parts/W25Q512JVEIQ/Winbond+Electronics/view-part/?ref=eda | 

