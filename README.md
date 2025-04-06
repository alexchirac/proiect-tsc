## Diagrama Bloc

![Diagrama Bloc](Images/Diagrama%20Bloc.png)

## Pin Assignments

| ESP32-C6 Pin | Function | Connected To | Description |
|--------------|----------|--------------|-------------|
| 3 | RESET | Reset Button | System hardware reset |
| 4 | SS_SD | SD Card (pin 2) | SPI Slave Select for SD card |
| 6 | SCK | SD Card (pin 5) | SPI Clock signal |
| 7 | MOSI | SD Card (pin 3) | SPI Master Out Slave In |
| 8 | INT_RTC | RTC Module (pin 3) | Interrupt signal from RTC |
| 9 | 32KHz | RTC Module (pin 1) | 32KHz clock signal from RTC |
| 13 | USB_D- | USB-C Connector (pin 3) | USB Data Negative line |
| 14 | USB_D+ | USB-C Connector (pin 1) | USB Data Positive line |
| 15 | IO/BOOT | Boot Button | Boot mode selector button |
| 16 | RTC_RST | RTC Module (pin 4) | RTC reset control |
| 17 | I2C_PW | BME688 Sensor (pins 6, 8, 2) | Power control for environmental sensor |
| 19 | SDA | Multiple I²C devices | I²C Serial Data line (shared) |
| 20 | SCL | Multiple I²C devices | I²C Serial Clock line (shared) |
| 23 | IO/CHANGE | Change Button | Display/Mode change button |
| 27 | MISO | SD Card (pin 7) | SPI Master In Slave Out |
