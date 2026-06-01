# Arduino I2C EEPROM Read & Write
### Interfacing Multiple 24LC256 EEPROM Memories via I2C

Old project: 2013.

![Platform](https://img.shields.io/badge/Platform-Arduino-blue)
![Language](https://img.shields.io/badge/Language-C%2B%2B-orange)
![IDE](https://img.shields.io/badge/IDE-Arduino%20IDE-blue)
![License](https://img.shields.io/badge/License-MIT-blue)

<p align="center"> <img src="assets/serial_monitor.png" width="450"> </p>

---

## Overview

This project demonstrates how to write and read data from two I2C EEPROM memories using the Arduino Uno.

The EEPROM (Electrically Erasable Programmable Read-Only Memory) devices used in this project are the Microchip 24LC256, which communicate through the I2C (Inter-Integrated Circuit) protocol.

Originally developed in 2013, this project has been reorganized and documented with improved clarity and structure.

It demonstrates several important embedded systems concepts:

- I2C communication protocol
- External non-volatile memory interfacing
- Addressing multiple devices on the same I2C bus
- Pull-up resistor configuration for SDA and SCL lines
- Serial data visualization via Serial Monitor

---

## Repository Structure

```text
Arduino_Read_Write_EEPROM_I2C_Memories/
│
├── assets/
│   ├── Diagrama_Eletrico_EEPROM.png
│   └── serial_monitor.png
│
├── src/
│   └── ReadWriteI2CMemories.ino
│
├── License
│
└── README.md
```

---

## Hardware Required

### Electronics

- 1 × Arduino Uno
- 2 × Microchip 24LC256 EEPROM
- 2 × 10 kΩ resistors (I2C pull-up for SDA and SCL)

### Miscellaneous

- Jumper wires
- Breadboard
- USB cable

---

## Hardware Setup

### EEPROM Devices

The 24LC256 is a 256 Kbit (32 KB) I2C serial EEPROM.

Multiple devices can share the same I2C bus by configuring different hardware addresses.

Each EEPROM requires:

- SDA and SCL connected to Arduino I2C pins
- 10 kΩ pull-up resistors on SDA and SCL
- WP (Write Protect) connected to GND to enable writing, or to VCC to disable writing (read-only mode)
- Proper power supply (5V and GND)

### Schematics

<p align="center"> <img src="assets/Diagrama_Eletrico_EEPROM.png" width="800"> </p>

---

## Wiring

#### Arduino to I2C Bus
| Arduino Pin | I2C Function | Connection |
|-------------|--------------|------------|
| A4          | SDA          | I2C Bus    |
| A5          | SCL          | I2C Bus    |
| 5V          | VCC          | I2C Bus    |
| GND         | GND          | I2C Bus    |

#### Pull-up Resistors
| Line  | Resistor Value | Connection |
|-------|----------------|------------|
| SDA   | 10 kΩ          | to 5V      |
| SCL   | 10 kΩ          | to 5V      |

#### Write Protect (WP) - EEPROM
| Connection Mode | WP Pin Connection |
|-----------------|-------------------|
| Write Enabled   | GND               |
| Read-Only Mode  | VCC               |


---

## How It Works

The firmware performs the following operations:

- Initializes the I2C interface
- Writes specific data to each EEPROM device
- Reads back the stored data
- Displays the results in the Serial Monitor

In the provided source code, data is written to devices with addresses:

- 0x51
- 0x52

These values are then displayed during testing.

The output format can be modified from:

- HEX (hexadecimal)
- OCT (octal)
- DEC (decimal)

by changing the Serial print formatting inside the code.

---

## Testing Procedure

- Connect the Arduino to the computer via USB
- Open the Serial Monitor in the Arduino IDE
- Observe the written and read values

---

## License

This project is open-source and available under the MIT License.

---

## Additional Notes

Originally developed in 2013 as an embedded systems learning project.

Documentation improved for clarity and educational purposes.
