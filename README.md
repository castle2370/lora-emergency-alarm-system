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

```
[LoRa SOS Button] ──LoRa 470MHz──► [LoRa Gateway + LCD]
                                          │
                                    CAT1 Cellular
                                          │
                                          ▼
                                   [EMQX MQTT Broker]
                                          │
                                    HTTP Auth + Node.js
                                          │
                              ┌───────────┴───────────┐
                              ▼                       ▼
                       [Telegram Bot]              [SMS Service]
```

> Photos of hardware will be added here.

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

## Communication Flow

1. User presses the SOS button
2. Button device transmits a LoRa packet (device ID + alarm type)
3. Gateway receives the packet and decodes it
4. Gateway triggers local buzzer + alarm linkage output
5. Gateway updates the LCD with alarm status
6. Gateway publishes an MQTT message to the cloud broker (via CAT1)
7. EMQX broker authenticates and routes the message
8. Node.js backend receives and processes the alarm event
9. Backend stores the event in MySQL and updates Redis
10. Telegram Bot and SMS notification are dispatched to the user

---

## RF Performance

- Tested with Keysight N9913A field analyzer
- Communication range: tested in open area and multi-floor building
- Frequency: 470 MHz, output power tuned per regulatory limit
- Sensitivity and link budget validated before deployment

---

## My Role

This was a solo end-to-end development project. My responsibilities included:

- Hardware schematic design and PCB prototype
- Embedded C firmware for both button device and gateway MCU
- SX1276 LoRa driver implementation and RF parameter tuning
- RF debugging using spectrum analyzer (Keysight N9913A)
- CAT1 module integration for cellular MQTT connectivity
- EMQX broker setup with HTTP device authentication
- Node.js backend API and alarm processing logic
- MySQL schema design and Redis caching for device state
- Telegram Bot integration for alarm push notifications
- End-to-end system testing and field validation

---

## Photos

> Hardware photos coming soon.

---

## Related Skills

`LoRa` `LORAWAN` `SX1276` `MQTT` `EMQX` `Embedded C` `Node.js`
`MySQL` `Redis` `CAT1` `NB-IoT` `RF Tuning` `IoT System Design`
