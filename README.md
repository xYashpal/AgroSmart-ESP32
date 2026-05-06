# 🌱 AgroSmart — Smart Irrigation System

Smart offline irrigation system for hilly regions
using ESP32, LoRa, and Raspberry Pi.

## Problem
Hilly region farmers waste water with manual irrigation.
No internet = cloud solutions fail.

## Solution
Automated soil moisture based irrigation.
Fully offline using LoRaWAN communication.
SMS alerts to farmer via GSM.

## Hardware Used
- ESP32 Dev Module
- DHT11 (Temperature + Humidity)
- Grove Soil Moisture Sensor
- DS3231 RTC Module
- Grove LoRa E5-HF (LoRaWAN)
- SIM800L GSM Module
- Single Channel Relay
- Buzzer

## Pin Connections
| Component | ESP32 Pin |
|---|---|
| DHT11 | GPIO4 |
| Moisture | GPIO34 |
| RTC SDA | GPIO21 |
| RTC SCL | GPIO22 |
| Buzzer | GPIO14 |
| Relay | GPIO13 |
| LoRa TX | GPIO16 |
| LoRa RX | GPIO17 |
| GSM RX | GPIO32 |
| GSM TX | GPIO33 |

## How It Works
1. ESP32 reads soil moisture every 2 seconds
2. If moisture below 40% → relay ON → pump waters crop
3. Data sent via LoRa to Raspberry Pi
4. Farmer gets SMS alert when irrigation starts/stops

## System Architecture
ESP32 → LoRa E5 → Raspberry Pi (DB + Intelligence)
ESP32 → SIM800L → Farmer SMS

## Features
- Fully offline (no internet needed)
- LoRaWAN range 2-15km
- SMS alerts via GSM
- RTC scheduled irrigation
- Buzzer alerts on site
- Solar power ready (future)

## Future Plans
- Raspberry Pi dashboard
- Solar power integration
- Multiple field nodes
- NPK sensor integration
