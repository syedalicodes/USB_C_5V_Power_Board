# USB_C_5V_Power_Board
A USB-C 5V power board with ESD protection, resettable fuse, reverse-polarity protection, and 3.3V regulation designed in KiCad 10.
# USB-C 5V Power Board

A compact USB-C 5V power board designed in KiCad 10 with input protection, reverse-polarity protection, a protected 5V output, and regulated 3.3V output.

![Final PCB 3D View](screenshots/01_Final_PCB_3D.png)

---

## 📌 Project Overview

This project is a custom USB-C power-management PCB designed as a practical electronics and PCB-design project.

The board accepts a nominal **5V USB-C input** and provides:

- Protected 5V output
- Regulated 3.3V output
- USB-C CC pull-down configuration
- Resettable overcurrent protection
- TVS transient-voltage protection
- P-channel MOSFET reverse-polarity protection
- Power-indicator LEDs

The complete schematic, PCB layout, manufacturing files, BOM, calculations, and testing procedure are included in this repository.

---

## ⚡ Block Diagram

```text
                    USB-C INPUT
                       5V
                        │
                        ▼
              ┌──────────────────┐
              │ CC1 / CC2       │
              │ 5.1kΩ Pull-down │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ Resettable PTC   │
              │ Fuse             │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ TVS Protection   │
              │ SMF5.0A          │
              └────────┬─────────┘
                       │
                       ▼
              ┌──────────────────┐
              │ AO3401A PMOS     │
              │ Reverse Polarity│
              └────────┬─────────┘
                       │
                  PROTECTED 5V
                       │
             ┌─────────┴─────────┐
             │                   │
             ▼                   ▼
        5V OUTPUT          AMS1117-3.3
                                │
                                ▼
                           3.3V OUTPUT
