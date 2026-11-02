# HeiChips 2025 SummerSchool – FPGA Carrier Board

This repository contains the KiCad hardware design for the **HeiChips 2025 SummerSchool FPGA Carrier Board**, designed to interface with the custom tapeout FPGA chip from the [HeiChips 2025 Tapeout Repository](https://github.com/HeiChips/heichips25-tapeout).

---

## 🏗 System Overview

The carrier board interfaces with a custom HeiChips FPGA breakout module via a 70-pin high-density mezzanine connector. An onboard RP2350A microcontroller handles FPGA configuration.

---

## ⚡ Key Hardware Features

### Onboard Controller & Configuration
* **Microcontroller:** RP2350A MCU managing FPGA boot configuration (`FPGA_CONFIG_SLOT[0..3]`), reset, clocks, and SPI interface.
* **Flash Memory:** Dual W25Q32JVSS QSPI Flash ICs (one for RP2350, one for FPGA image storage).
* **Control Switches:** 74LVC1G66 analog switch for SPI bus arbitration.

### Power Management
* **Input Power:** 5V DC input via USB-C
* **System 3.3V:** TLV1117-33 LDO supplying 3.3V rail from 5V input for FPGA IO and Microcontroller
* **FPGA Core Supply (`VCORE`/`AVCORE`):** AP7361C adjustable LDO 

### Connectors & Peripherals
* **Module Interconnect:** 70-pin Amphenol BergStak Mezzanine Receptacle (`10164227-0701A1RLF`).
* **Expansion:** 4x PMOD headers (`J20`–`J23`) routing FPGA `GPIO0`–`GPIO31`.
* **Video Output:** HDMI interface (`J18`) driven by DS90LV027A LVDS differential line drivers.
* **USB Ports:** Dual USB-C connectors (`J17` for RP2350 debug/programming, `J19` directly connected to FPGA USB with ESD protection).
* **Analog & RF:** Coaxial SMA/MCX connectors for IceLab analog pins, internal analog signals, and Pudding I/O lines.
* **Ethernet:** 3-pin Ethernet header (`J8`).

---

## TODO
[ ] HDMI differential pair length matching and impedance tuning.
[ ] Project selection per jumper
[ ] Connect GPIOs from FPGA to Microcontroller UART? 
[ ] Check SMA distance

---

## 👤 Author
* **Konrad Bode** 
