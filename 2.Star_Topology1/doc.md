# Lab 02 - Basic Star Topology

This is a Cisco Packet Tracer lab created as part of my CCNA learning journey.

## 📝 Lab Overview

In this lab, I practiced building a basic **star network topology** using a central network switch.

The switch acts as the central connection point, and all end devices are connected directly to the switch. The network uses the address space `172.16.16.0/24`.

## 🧰 Devices & Equipment

- 1x Cisco Catalyst Switch
- 2x PC
- 1x Laptop
- 1x Server
- 1x IP Phone
- 1x additional end device
- Ethernet cables

## 🎯 Objectives

The main objectives of this lab were:

- Get familiar with Cisco Packet Tracer
- Understand the structure of a star topology
- Understand the role of a central network switch
- Connect multiple end devices to a single switch
- Practice identifying switch interfaces
- Understand basic MAC address information
- Practice building a simple Ethernet network
- Use the `172.16.16.0/24` network

## ⭐ Star Topology

In a star topology, all end devices are connected to a central network device, usually a switch.

```text
                         ┌─────────────┐
                         │    PC /     │
                         │ End Device  │
                         └──────┬──────┘
                                │
                                │ Fa0/1
                                │
        ┌─────────────┐         │         ┌─────────────┐
        │     PC      │─────────┤         │   Server    │
        └─────────────┘ Fa0/2   │         └──────┬──────┘
                                │                │
                         ┌──────┴──────┐         │
                         │    Cisco    │─────────┘
                         │   Switch    │
                         └──┬────┬────┬┘
                            │    │    │
                         Fa0/3 Fa0/4 Fa0/5
                            │    │    │
                         ┌──┘    │    └────────────┐
                         │       │                 │
                    ┌────┴───┐ ┌─┴──────┐     ┌───┴──────┐
                    │ Laptop │ │ Device │     │ IP Phone │
                    └────────┘ └────────┘     └──────────┘
```

## 🌐 Network Information

- Network: `172.16.16.0/24`
- Topology: Star
- Central Device: Network Switch
- Communication Type: Ethernet

## 🔌 Switch Connections

The devices are connected to different switch interfaces:

| Switch Port | Connected Device |
| ----------- | ---------------- |
| Fa0/1       | End device       |
| Fa0/2       | PC               |
| Fa0/3       | Laptop           |
| Fa0/4       | End device       |
| Fa0/5       | IP Phone         |
| Gi0/1       | Server           |

## 🔑 MAC Addresses

The MAC addresses shown in the topology are:

| Device     | MAC Address      |
| ---------- | ---------------- |
| PC         | `0001.429D.2DB3` |
| PC         | `00D0.BAA1.7AAD` |
| Laptop     | `0001.42DC.C0A1` |
| End device | `0060.3E47.C268` |
| Server     | `0090.0C08.7BAD` |

## 📌 Topology Characteristics

The main characteristic of this topology is that all devices have a direct connection to the central switch.

If one end-device cable fails, only that device loses its connection. However, if the central switch fails, communication between all connected devices is affected.

## 🧪 Lab Practice

During this lab, I practiced:

- Creating a star topology in Cisco Packet Tracer
- Connecting end devices to a central switch
- Identifying Fast Ethernet and Gigabit Ethernet interfaces
- Working with MAC addresses
- Understanding the physical structure of a small Ethernet network
