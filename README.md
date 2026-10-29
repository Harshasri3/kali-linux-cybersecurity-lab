# Kali Linux Cybersecurity Lab

I set up Kali Linux in Oracle VirtualBox on my Windows computer. I configured the network, tested the connection, and set up a shared folder and a few VirtualBox convenience options.

## What I used

- Oracle VirtualBox
- Kali Linux
- Windows host computer

## My setup

- VirtualBox NAT Network: `NatNetwork`
- Network range: `10.0.0.0/24`
- Kali IP address: `10.0.0.2/24`
- Gateway: `10.0.0.1`
- DNS: `8.8.8.8`
- Shared host folder: `Downloads`
- Shared clipboard and drag-and-drop: Bidirectional

### Problem I Faced with NAT Networking

While setting up the NAT Network in VirtualBox, I faced a network connectivity issue in Kali Linux. After configuring the static IP address `10.0.0.2`, Kali initially showed that the IP address was already in use, and I couldn't reach the gateway at `10.0.0.1`.

I checked the network configuration, reconnected the network interface, and verified the IP address and default route. After fixing the configuration, I was able to ping the gateway and `8.8.8.8` successfully. I also tested internet connectivity by pinging `google.com`.

This helped me understand how to configure a NAT Network, assign a static IP address, and troubleshoot basic network connectivity issues.

## Screenshots

1. `01-virtualbox-nat-network-settings.png` — NAT Network settings in VirtualBox.
2. `02-kali-running-in-virtualbox.png` — Kali Linux running in its virtual machine.
3. `03-kali-static-ip-configuration.png` — Manual IPv4 settings for Kali.
4. `04-kali-static-ip-and-connectivity-test.png` — Kali IP and route details, plus ping tests to the gateway and `8.8.8.8`.
5. `05-kali-internet-connectivity-test.png` — Successful ping test to `google.com`.
6. `06-virtualbox-clipboard-drag-drop-settings.png` — Clipboard and drag-and-drop set to Bidirectional.
7. `07-virtualbox-shared-folder-settings.png` — Host Downloads folder being added as a shared folder.
8. `08-virtualbox-kali-snapshot.png` — Snapshot named `Kali - Initial Lab Setup`.

## Commands I used to check the network

```bash
ip -4 addr show eth0
ip route
ping -c 4 10.0.0.1
ping -c 4 8.8.8.8
ping -c 4 google.com
```

The screenshots show the network checks succeeding at the time I ran them. Network settings can change, so I would run the commands again if I need to check the setup later.

## Notes

This repository records my own VirtualBox and Kali Linux setup. It is a small practice lab for learning Linux and networking basics. Any security testing should be done only on systems I own or have permission to test.
