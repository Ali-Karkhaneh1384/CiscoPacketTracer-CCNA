# Lab 04 - Default Gateway

This is a Cisco Packet Tracer lab created as part of my CCNA learning journey.

## 📝 Lab Overview

In this lab, I practiced the concept of the **Default Gateway** and how it allows devices in different networks to communicate with each other.

The topology consists of two separate LANs connected through a router.

- Left Network: `192.168.1.0/24`
- Right Network: `192.168.2.0/24`

Each network has its own Default Gateway configured on the router.

## 🧰 Devices & Equipment

- 1x Router
- 2x Cisco Switches
- 2x PCs
- 2x Laptops
- Ethernet cables

## 🎯 Objectives

The main objectives of this lab were:

- Understand the concept of a Default Gateway
- Understand why hosts need a Default Gateway
- Configure router interfaces as Default Gateways
- Connect two different IP networks using a router
- Understand how a host communicates with devices outside its local network
- Practice IP addressing and subnet masks

## 🌐 Network Information

### Left Network

- Network: `192.168.1.0/24`
- Default Gateway: `192.168.1.1`
- Router Interface: `Gig0/0/0`

### Right Network

- Network: `192.168.2.0/24`
- Default Gateway: `192.168.2.1`
- Router Interface: `Gig0/0/1`

## 🚪 What is a Default Gateway?

A **Default Gateway** is the device that a host sends traffic to when the destination is outside of its local network.

In this topology, the router acts as the Default Gateway for both networks.

For devices in the `192.168.1.0/24` network, the Default Gateway is `192.168.1.1`.

For devices in the `192.168.2.0/24` network, the Default Gateway is `192.168.2.1`.

## 🔀 How Does the Default Gateway Work?

Suppose a PC in the `192.168.1.0/24` network wants to communicate with a PC in the `192.168.2.0/24` network.

The source PC first checks whether the destination belongs to its own local network.

Since `192.168.2.x` is not part of the `192.168.1.0/24` network, the PC sends the packet to its Default Gateway, which is `192.168.1.1`.

The router receives the packet and forwards it toward the `192.168.2.0/24` network.

The communication path is:

`192.168.1.x → 192.168.1.1 → Router → 192.168.2.1 → 192.168.2.x`

## 📡 Local vs Remote Communication

If a host communicates with another device in the same network, it does not need to send the packet to the Default Gateway.

For example:

`192.168.1.10 → 192.168.1.20`

Both devices belong to the `192.168.1.0/24` network, so the communication is local.

However, if the destination is `192.168.2.10`, the destination belongs to another network.

Therefore, the source host sends the traffic to `192.168.1.1`, which is its Default Gateway.

## 🧪 Lab Practice

During this lab, I practiced:

- Creating two separate LANs
- Connecting end devices to switches
- Connecting switches to a router
- Understanding IP networks
- Understanding `/24` subnet masks
- Configuring Default Gateways
- Understanding local network communication
- Understanding communication between different networks
- Understanding the role of a router as a Default Gateway

## 📌 Key Concept

The **Default Gateway** is used when a host needs to communicate with a destination outside of its local network.

In this topology:

`192.168.1.0/24 → Gateway: 192.168.1.1 → Router → Gateway: 192.168.2.1 → 192.168.2.0/24`

The router provides the Layer 3 connection between the two different networks.

## 💡 Important Note

A Default Gateway does not necessarily mean the Internet.

The Default Gateway is simply the device that a host uses to reach destinations outside its local network.

In this lab, the router is the Default Gateway because it is responsible for routing traffic between the two different networks.
