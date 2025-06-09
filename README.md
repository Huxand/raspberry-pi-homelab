# raspberry-pi-homelab

# Pi-hole DNS Sinkhole + Docker-Powered Homelab on Raspberry Pi 5

This project documents the setup and deployment of a network-wide DNS sinkhole using **Pi-hole** running in a **Docker container** on a **Raspberry Pi 5**. It is part of my ongoing cybersecurity homelab initiative to strengthen skills in network monitoring, DNS filtering, containerization, and system administration.

---

##  Project Goals

- Deploy a low-cost, low-power DNS filtering server using Pi-hole
- 24/7 Run services in isolated Docker containers for modularity and control
- Configure a secure homelab network for hands-on cybersecurity practice
- Document and showcase practical experience for recruiters

---

## ⚙️ Tech Stack

| Component        | Description |
|------------------|-------------|
|  **Raspberry Pi 5** | Hardware platform running Raspberry Pi OS lite (64-bit) |
|  **Cockpit** | Web-based graphical interface for managing Linux servers  |
|  **Docker**         | Containerization for isolated services |
|  **Portainer**      | GUI management of Docker containers |
|  **Pi-hole**        | DNS-based ad/tracker blocker running in Docker |
|  **Custom Firewall Rules** | Basic network hardening practices |

---

## Setup Overview

1. Flashed Raspberry Pi OS (Lite) to a 128GB microSD
2. Connected Pi to network via Ethernet
3. Installed updates, Docker, and Portainer
4. Deployed Pi-hole using Docker
5. Configured static IP and custom DNS settings on router
6. Applied blocklists and tested DNS resolution

---

## 🔍 Key Configuration

## Pi-hole Container Configuration

This container was created in Portainer using the following configuration:

- **Image**: `pihole/pihole:latest`
- **Environment Variables**:
  - `TZ=America/Phoenix`
  - `WEBPASSWORD=<hidden>`
- **Ports**: 53 TCP/UDP, 80
- **Volumes**:
  - `/etc/pihole`
  - `/etc/dnsmasq.d`
- **Network**: Custom Macvlan 
- **Restart Policy**: `unless-stopped`
