This guide is for those looking for a deeper understanding of ShellHub.

If you are looking for instructions on how to set up ShellHub
for your device fleet, check out the [Getting Started](getting-started.md).

## Basic concepts

There are few basic concepts that are important to understand the ShellHub.
Those basic concepts are detailed below:

**SSHID**

SSHID is a unique address to identify a device in ShellHub SSH gateway.

SSHID consist of following format:

    <NAMESPACE>.<DEVICE_NAME>@<GATEWAY_ADDRESS>

Where:

1. `<NAMESPACE>`: Is the account namespace identifier
2. `<DEVICE_NAME>`: Is the device name identifier
3. `<GATEWAY_ADDRESS>`: Is the gateway address identifier

Example of SSHID: `lab.rasp-1@localhost`