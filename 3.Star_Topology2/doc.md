# Lab 03 - Routed Star Network Topology

This is a Cisco Packet Tracer lab created as part of my CCNA learning journey.

## 📝 Lab Overview

In this lab, I practiced building a routed network consisting of two separate star-shaped LANs connected through a central router.

Each LAN uses a different `/24` network, and the router provides the default gateway for both networks.

- Left LAN: `172.16.16.0/24`
- Right LAN: `172.16.17.0/24`

The central router connects the two networks through two Gigabit Ethernet interfaces.

## 🧰 Devices & Equipment

- 1x Router
- 3x Switches
- 4x PCs
- 2x Laptops
- Ethernet cables

## 🎯 Objectives

The main objectives of this lab were:

- Build two separate LANs in Cisco Packet Tracer
- Create star topologies using switches
- Connect two different networks through a router
- Configure router interfaces
- Understand the role of a default gateway
- Identify network addresses and host addresses
- Practice connecting switches to a router
- Understand communication between different IP networks

## 🌐 Network Information

### Left Network

- Network: `172.16.16.0/24`
- Default Gateway: `172.16.16.1`
- Router Interface: `Gig0/0/0`

### Right Network

- Network: `172.16.17.0/24`
- Default Gateway: `172.16.17.1`
- Router Interface: `Gig0/0/1`

## 🗺️ Topology

```text
                         ┌──────────────┐
                         │    Router    │
                         │              │
                         │ G0/0/0 G0/0/1│
                         └──────┬───┬───┘
                                │   │
                  172.16.16.0/24   │   172.16.17.0/24
                                │   │
                         ┌──────┘   └──────┐
                         │                 │
                    ┌────┴────┐       ┌───┴────┐
                    │ Switch  │       │ Switch │
                    └───┬─────┘       └───┬────┘
                       /   \              /   \
                      /     \            /     \
                    PC     Laptop       PC     Laptop
```

The left side contains an additional switch connected to the central switch, creating a larger LAN while maintaining the star-based structure.

## 🔌 Main Connections

### Router

| Interface | Network          | Gateway       |
| --------- | ---------------- | ------------- |
| Gig0/0/0  | `172.16.16.0/24` | `172.16.16.1` |
| Gig0/0/1  | `172.16.17.0/24` | `172.16.17.1` |

### Left Network

| Device | IP Address     |
| ------ | -------------- |
| PC     | `172.16.16.10` |
| Laptop | `172.16.16.11` |
| PC     | `172.16.16.12` |
| Laptop | `172.16.16.13` |

### Right Network

| Device | IP Address     |
| ------ | -------------- |
| PC     | `172.16.17.10` |
| Laptop | `172.16.17.11` |

## 🔑 MAC Addresses

The topology shows the following MAC addresses:

- `00D0.BC0E.6D01`
- `00D0.BC0E.6D02`
- `0030.A36A.6B1A`
- `000C.CF5C.3C97`

## 📡 Default Gateway

The router acts as the default gateway for the hosts in each network.

For devices in `172.16.16.0/24`, the gateway is:

```text
172.16.16.1
```

For devices in `172.16.17.0/24`, the gateway is:

```text
172.16.17.1
```

When a host needs to communicate with a device in another network, it sends the traffic to its default gateway, which is the router.

## 🧪 Lab Practice

During this lab, I practiced:

- Creating multiple LANs
- Connecting switches together
- Connecting switches to a router
- Assigning IP addresses to end devices
- Understanding `/24` networks
- Configuring router interfaces
- Setting default gateways
- Understanding how a router connects different networks
- Building a routed network topology in Cisco Packet Tracer

## 📌 Key Concept

A switch is mainly used to connect devices within the same local network, while a router is used to connect different IP networks.

In this topology:

```text
172.16.16.0/24  ←→  Router  ←→  172.16.17.0/24
```

The router provides the Layer 3 connection between the two LANs.
