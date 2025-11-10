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

### 3. Update System
Run the following commands to update your system:

sudo apt update && sudo apt upgrade -y

### 4. Install Pi-hole
Run the automated installer:

curl -sSL https://install.pi-hole.net | bash

### 5. Configure Router DNS
- Log into your router’s admin panel
- Set Primary DNS to your Pi-hole IP address
- Disable IPv6 DNS or configure it to use Pi-hole if supporte

### 6. Verify Installation
Check Pi-hole status:

pihole status

Optional: Install Unbound
Unbound improves privacy by resolving DNS queries recursively.
- Install Unbound: 

sudo apt install -y unbound



