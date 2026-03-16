# LoRa Emergency Alarm System with MQTT Cloud Notification

![IoT](https://img.shields.io/badge/IoT-LoRa%20%2B%20MQTT-blue)
![Firmware](https://img.shields.io/badge/Firmware-C%20Embedded-green)
![Backend](https://img.shields.io/badge/Backend-Node.js-brightgreen)
![Status](https://img.shields.io/badge/Status-Deployed-success)

A complete end-to-end LoRa-based emergency alarm system for industrial
and building safety applications — from wireless hardware design to
cloud notification delivery.

---

## Overview

This project covers the full development lifecycle of a wireless emergency
alarm system: hardware prototype design, embedded firmware, RF tuning,
gateway communication, MQTT cloud integration, and real-time notification.

When an emergency button is pressed, the system delivers an alert to
the end user within seconds via Telegram Bot or SMS, with zero reliance
on Wi-Fi infrastructure.

---

## System Architecture

![System Architecture](LoRa%20Emergency%20Alarm%20System%20Architecture.jpg)

---

## Communication Flow

![Alarm Flow](LoRa%20Emergency%20Alarm%20Flow.jpg)

---

## Hardware Components

| Component | Description |
|---|---|
| LoRa Gateway | MCU + SX1276 transceiver, 128×64 LCD display, CAT1 cellular |
| SOS Button Device | MCU + SX1276, battery-powered, low power design |
| Alarm Output | Local buzzer + sound/light alarm linkage |
| RF Frequency | 470 MHz (CN standard) |

---

## Software Stack

| Layer | Technology |
|---|---|
| Device Firmware | Embedded C (MCU) |
| LoRa Protocol | Custom packet protocol over SX1276 |
| Cloud Connectivity | MQTT over CAT1 cellular |
| MQTT Broker | EMQX with HTTP authentication |
| Backend | Node.js |
| Database | MySQL + Redis |
| Notifications | Telegram Bot API + SMS gateway |

---

## Key Features

- Long-range LoRa wireless — no Wi-Fi or local network required
- Real-time alarm reporting via MQTT publish/subscribe
- LCD display showing device ID and live alarm status
- Gateway-triggered local sound and light alarm linkage
- Telegram and SMS push notifications on alarm event
- Battery-powered button devices with multi-year battery life
- EMQX broker with HTTP-based device authentication

---

## RF Performance

- Tested with Keysight N9913A field analyzer
- Frequency: 470 MHz, output power tuned per regulatory limit
- Sensitivity and link budget validated before deployment

---

## My Role

This was a solo end-to-end development project. My responsibilities included:

- Hardware schematic design and PCB prototype
- Embedded C firmware for both button device and gateway MCU
- SX1276 LoRa driver implementation and RF parameter tuning
- RF debugging using Keysight N9913A spectrum analyzer
- CAT1 module integration for cellular MQTT connectivity
- EMQX broker setup with HTTP device authentication
- Node.js backend API and alarm processing logic
- MySQL schema design and Redis caching for device state
- Telegram Bot integration for alarm push notifications
- End-to-end system testing and field validation

---

## Photos

![Photo 1](images/P1_1.jpg)
![Photo 2](images/P1_2.jpg)
![Photo 3](images/P1_3.jpg)
![Photo 4](images/P1_4.jpg)
![Photo 5](images/P1_5.jpg)

---

## Related Skills

`LoRa` `LORAWAN` `SX1276` `MQTT` `EMQX` `Embedded C` `Node.js`
`MySQL` `Redis` `CAT1` `NB-IoT` `RF Tuning` `IoT System Design`
