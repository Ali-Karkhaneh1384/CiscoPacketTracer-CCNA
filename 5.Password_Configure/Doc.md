# Lab 05 - Cisco Device Password Configuration

This is a Cisco Packet Tracer lab created as part of my CCNA learning journey.

## 📝 Lab Overview

In this lab, I practiced configuring passwords on Cisco network devices to control access to different modes and connection methods.

Cisco devices can use passwords for Privileged EXEC mode, Console access, and VTY remote access.

## 🎯 Objectives

The main objectives of this lab were:

- Configure a password for Privileged EXEC mode
- Configure a password for Console access
- Configure passwords for VTY lines
- Understand the difference between `enable password` and `enable secret`
- Enable password checking using the `login` command
- Encrypt plain-text passwords using `service password-encryption`
- Practice basic Cisco device security

## 🔐 Privileged EXEC Password

The `enable secret` command is used to protect Privileged EXEC mode.

`Router(config)# enable secret cisco`

After configuring the password, the device asks for the password when entering Privileged EXEC mode.

`Router> enable`

`Password:`

`Router#`

`enable secret` is preferred over `enable password` because it stores the password in a more secure hashed form.

## 🖥️ Console Password

To configure a password for Console access:

`Router(config)# line console 0`

`Router(config-line)# password console123`

`Router(config-line)# login`

The `login` command tells the device to require the configured password when accessing the device through the Console.

## 🌐 VTY Password

VTY lines are used for remote access to a Cisco device, such as Telnet or SSH.

To configure a password for VTY lines:

`Router(config)# line vty 0 4`

`Router(config-line)# password vty123`

`Router(config-line)# login`

The `login` command enables password checking for the VTY lines.

## 🔒 Password Encryption

The following command encrypts passwords that would otherwise appear in plain text in the configuration:

`Router(config)# service password-encryption`

## 🧪 Complete Configuration

`Router> enable`

`Router# configure terminal`

`Router(config)# enable secret cisco`

`Router(config)# line console 0`

`Router(config-line)# password console123`

`Router(config-line)# login`

`Router(config-line)# exit`

`Router(config)# line vty 0 4`

`Router(config-line)# password vty123`

`Router(config-line)# login`

`Router(config-line)# exit`

`Router(config)# service password-encryption`

`Router(config)# end`

## 🔍 Verifying the Configuration

The current configuration can be viewed using:

`Router# show running-config`

This command displays the running configuration of the Cisco device.

## 📌 Important Commands

| Command                       | Purpose                            |
| ----------------------------- | ---------------------------------- |
| `enable secret <password>`    | Configure Privileged EXEC password |
| `enable password <password>`  | Configure an enable password       |
| `line console 0`              | Enter Console line configuration   |
| `line vty 0 4`                | Enter VTY line configuration       |
| `password <password>`         | Configure a line password          |
| `login`                       | Enable password checking           |
| `service password-encryption` | Encrypt plain-text line passwords  |
| `show running-config`         | Display the current configuration  |

## 💡 Key Concepts

### `enable secret`

Protects access to Privileged EXEC mode and is preferred over `enable password`.

### `line console 0`

Used to configure access through the physical Console connection.

### `line vty 0 4`

Used to configure remote access through VTY lines.

### `login`

Tells the Cisco device to ask for the password configured on the line.

### `service password-encryption`

Encrypts passwords that would otherwise be displayed in plain text in the configuration.

## 🧠 Lab Summary

In this lab, I learned how to secure different access methods on a Cisco network device.

Cisco Device → Privileged EXEC → `enable secret`

Cisco Device → Console Access → `line console 0` → `password + login`

Cisco Device → Remote Access → `line vty 0 4` → `password + login`

Password configuration is an important basic step for securing Cisco network devices.
