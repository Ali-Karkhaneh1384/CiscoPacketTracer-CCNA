# Lab 06 - Static Routing and Routing Table

This is a Cisco Packet Tracer lab created as part of my CCNA learning journey.

## 📝 Lab Overview

In this lab, I practiced **Static Routing** and learned how routers use their **Routing Table** to determine the best path for forwarding packets.

The topology consists of two routers connected through the `10.11.12.0/24` network.

Each router is also connected to one or more local networks.

## 🌐 Network Topology

The networks used in this lab are:

- `10.10.1.0/24`
- `10.10.2.0/24`
- `10.11.12.0/24`
- `10.10.3.0/24`

The topology can be summarized as:

`10.10.1.0/24 → R1 → 10.11.12.0/24 → R2 → 10.10.3.0/24`

The `10.10.2.0/24` network is also directly connected to R1.

## 🎯 Objectives

The main objectives of this lab were:

- Understand the concept of Static Routing
- Understand how a Routing Table works
- Identify directly connected networks
- Configure Static Routes
- Understand the Next-Hop address
- Understand how routers forward packets
- Verify routing information using the Routing Table
- Test connectivity between different networks

## 🗺️ Network Information

### Router 1

Router 1 is connected to three networks:

- `10.10.1.0/24`
- `10.10.2.0/24`
- `10.11.12.0/24`

Router 1 interfaces:

- `Gig0/0` → `10.10.1.1`
- `Gig0/1` → `10.10.2.1`
- `Gig0/3/0` → `10.11.12.1`

### Router 2

Router 2 is connected to:

- `10.11.12.0/24`
- `10.10.3.0/24`

Router 2 interfaces:

- `Gig0/3/0` → `10.11.12.2`
- `Gig0/0` → `10.10.3.1`

## 📋 Routing Table

A router stores information about available networks in its **Routing Table**.

The router uses the Routing Table to determine where packets should be forwarded.

For example, Router 1 knows that the following networks are directly connected:

- `10.10.1.0/24`
- `10.10.2.0/24`
- `10.11.12.0/24`

However, Router 1 does not have a direct connection to:

- `10.10.3.0/24`

Therefore, a route must be configured so that Router 1 knows how to reach the `10.10.3.0/24` network.

## 🔀 Static Route

A Static Route is a route manually configured by the network administrator.

The basic syntax is:

`ip route <destination-network> <subnet-mask> <next-hop>`

For example, on Router 1:

`R1(config)# ip route 10.10.3.0 255.255.255.0 10.11.12.2`

This tells Router 1:

"If you need to reach the `10.10.3.0/24` network, send the packet to `10.11.12.2`."

## 🔁 Route on Router 2

Router 2 also needs to know how to reach the networks behind Router 1.

For example:

`R2(config)# ip route 10.10.1.0 255.255.255.0 10.11.12.1`

And:

`R2(config)# ip route 10.10.2.0 255.255.255.0 10.11.12.1`

This tells Router 2 to forward traffic destined for the networks behind Router 1 to `10.11.12.1`.

## 🧪 Static Routing Configuration

### Router 1

`R1(config)# ip route 10.10.3.0 255.255.255.0 10.11.12.2`

### Router 2

`R2(config)# ip route 10.10.1.0 255.255.255.0 10.11.12.1`

`R2(config)# ip route 10.10.2.0 255.255.255.0 10.11.12.1`

## 🔍 Verifying the Routing Table

The Routing Table can be displayed using:

`R1# show ip route`

or:

`R2# show ip route`

The output contains different types of routes.

For example:

- `C` = Connected
- `L` = Local
- `S` = Static

A Static Route appears with the `S` code.

Example:

`S    10.10.3.0/24 [1/0] via 10.11.12.2`

This means that the route to `10.10.3.0/24` is a Static Route and the next-hop address is `10.11.12.2`.

## 🧭 How Packet Forwarding Works

Suppose a PC in the `10.10.1.0/24` network wants to communicate with a PC in the `10.10.3.0/24` network.

The packet follows this path:

`PC → R1 → R2 → Destination PC`

More specifically:

`10.10.1.x → 10.10.1.1 → 10.11.12.2 → 10.10.3.1 → 10.10.3.x`

R1 checks its Routing Table and finds a Static Route for `10.10.3.0/24`.

The next hop is `10.11.12.2`, which belongs to R2.

R2 then receives the packet and forwards it to the `10.10.3.0/24` network.

## 📌 Directly Connected vs Static Routes

A directly connected network is automatically added to the Routing Table when the router interface is configured with an IP address and is up.

For example, R1 directly connects to:

`10.10.1.0/24`

`10.10.2.0/24`

`10.11.12.0/24`

A Static Route, however, must be manually configured by the administrator.

For example:

`10.10.3.0/24 → 10.11.12.2`

## 🧠 Key Concepts

### Routing Table

The Routing Table contains information about networks that the router knows how to reach.

### Static Route

A route manually configured by the administrator.

### Next Hop

The IP address of the next router to which the packet should be forwarded.

### Connected Route

A route automatically created for a network directly connected to a router interface.

## 🧪 Lab Practice

During this lab, I practiced:

- Configuring router interfaces
- Understanding directly connected networks
- Configuring Static Routes
- Understanding Next-Hop addresses
- Reading the Routing Table
- Using `show ip route`
- Identifying `C`, `L`, and `S` routes
- Understanding how routers forward packets
- Testing communication between different networks

## 📌 Important Commands

| Command                                | Purpose                                   |
| -------------------------------------- | ----------------------------------------- |
| `ip route <network> <mask> <next-hop>` | Configure a Static Route                  |
| `show ip route`                        | Display the Routing Table                 |
| `show ip interface brief`              | Display interface status and IP addresses |
| `ping <ip-address>`                    | Test connectivity                         |
| `traceroute <ip-address>`              | Display the path toward a destination     |

## 💡 Lab Summary

In this lab, I learned that a router uses its Routing Table to decide where packets should be forwarded.

If the destination network is directly connected, the router can forward the packet directly.

If the destination network is not directly connected, the router needs a route to that network.

In Static Routing, this route is manually configured by the administrator.

The main concept of this lab can be summarized as:

`Destination Network → Routing Table → Next Hop → Forward Packet`

Static Routing is a basic but important concept for understanding how routers make forwarding decisions.
