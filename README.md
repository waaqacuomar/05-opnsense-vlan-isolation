# Isolating My Lab with OPNsense and VLANs

The lab runs on its own VLAN behind an OPNsense firewall, so break/fix experiments can't touch my home network.

## Setup
- OPNsense 26.7 as a Proxmox VM (4 vCPUs)
- WAN on the home network, LAN on the lab VLAN (10.10.10.0/24)
- Netgear GS108Ev4 managed switch in 802.1Q mode, VLAN 10 "LAB" tagged on the Proxmox node's port
- Proxmox bridges made VLAN-aware
- Unbound DNS on OPNsense for the lab

## Firewall rules
- Lab VLAN is blocked from reaching the home network
- Lab still has internet access and working DNS

## Why
I break things on purpose to practice. Isolation means a mistake in the lab stays in the lab.

## Screenshots
![OPNsense dashboard](images/opnsense.png)
![Managed switch](images/switch.png)
