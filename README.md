# pi-hole-on-pi4
Harden your home network with Pi-hole on Raspberry Pi 4 — block ads, trackers, and take control of DNS.

---

## 🧰 Hardware Requirements

- Raspberry Pi 4 (4GB RAM)
- 64GB microSD card
- 18W USB-C power supply
- Ethernet connection (recommended)
- Raspberry Pi case with cooling (fan or heatsinks)

---

## 📦 Software Requirements

- Raspberry Pi OS Lite (64-bit recommended)
- Pi-hole (latest version)
- Optional: Unbound DNS resolver

---

## 🚀 Installation Steps

### 1. Flash Raspberry Pi OS

- Download [Raspberry Pi Imager](https://www.raspberrypi.com/software/)
- Choose **Raspberry Pi OS Lite (64-bit)**
- Flash to microSD card
- Enable SSH by placing an empty file named `ssh` in the boot partition

### 2. Boot and Connect

- Insert microSD card and power on the Pi
- Connect via SSH:
  ```bash
  ssh pi@<raspberry_pi_ip>
