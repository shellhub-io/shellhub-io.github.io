---
hide:
  - navigation
---

ShellHub is a modern SSH server for remotely accessing Linux devices
via command line (using any SSH client) or web-based user interface.
It is intended to be used instead of _sshd_.

Typically, if you want to SSH a Linux device on a local network,
you just need to know its IP address.
However, in order to access a Linux device from outside the local network,
you will have to go through a few inconveniences, such as getting its public IP
address and configuring the router.
Changing the VPN/firewall configuration can be cumbersome if the device
is behind a corporate firewall that does not allow SSH connections.

ShellHub provides a way to avoid all these hassles, helping you easily and seamlessly access
any Linux device behind firewall and NAT.

![Screenshot](img/screenshot.png){:.shadow}

## Overview

This introduction section is intended to give a high-level overview of the ShellHub.

![Diagram](img/diagram.png){:.shadow}

<center>*[Click here](img/diagram.png)* to view large image</center>

There are few basic concepts that are important to understand the ShellHub.
Those basic concepts are detailed below:

### SSH Gateway

The SSH gateway is a SSH server which forward connections to the devices
running ShellHub's agent.

### Device

An internet-connected device, such as a computer or something more specific like a single-board computer, running ShellHub's agent.

### Agent

ShellHub's agent which must be installed on the device.

### SSHID

SSHID is a unique address to identify a device in the SSH gateway, which must
be specified in the following format:

    <NAMESPACE>.<HOSTNAME>@<SERVER_ADDRESS>

Where:

* `<NAMESPACE>`: Is the account namespace identifier
* `<HOSTNAME>`: Is the device hostname identifier
* `<SERVER_ADDRESS>`: Is the ShellHub server instance address identifier

!!! info "Example of SSHID: `demo.device-1@cloud.shellhub.io`"
