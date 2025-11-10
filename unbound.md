# Unbound DNS Resolver Setup for Pi-hole

Unbound is a lightweight, secure, and privacy-focused DNS resolver that works perfectly alongside Pi-hole. It allows your Raspberry Pi to resolve DNS queries directly from authoritative servers, eliminating reliance on third-party DNS providers.

---

## 🧰 Requirements

- Raspberry Pi 4 with Pi-hole already installed
- Raspberry Pi OS Lite (64-bit)
- Internet access

---

## 📦 Install Unbound

Update your package list and install Unbound:

```bash
sudo apt update
sudo apt install -y unbound

📁 Configure Unbound
Create a configuration file for Pi-hole:
sudo nano /etc/unbound/unbound.conf.d/pi-hole.conf


Paste the following configuration:
server:
    verbosity: 1
    interface: 127.0.0.1
    port: 5335
    do-ip4: yes
    do-udp: yes
    do-tcp: yes
    root-hints: "/var/lib/unbound/root.hints"
    harden-glue: yes
    harden-dnssec-stripped: yes
    use-caps-for-id: yes
    edns-buffer-size: 1232
    prefetch: yes
    num-threads: 1
    so-rcvbuf: 1m
    cache-min-ttl: 3600
    cache-max-ttl: 86400
    rrset-roundrobin: yes

🌍 Download Root DNS Hints
Unbound uses root DNS servers to resolve queries. Download the latest list:
wget -O /var/lib/unbound/root.hints https://www.internic.net/domain/named.root

🔁 Restart and Enable Unbound
sudo systemctl restart unbound
sudo systemctl enable unbound

🛠️ Configure Pi-hole to Use Unbound
- Open the Pi-hole Admin Panel
- Go to Settings → DNS
- Under Custom 1 (IPv4), enter:
127.0.0.1#5335
- Uncheck other upstream DNS providers

✅ Test Unbound
Run a test query to verify Unbound is working:
dig pi-hole.net @127.0.0.1 -p 5335


You should see a status: NOERROR and a response time.
