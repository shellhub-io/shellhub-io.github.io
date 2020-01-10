The ShellHub is composed of two major parts, the **SSH gateway** and the **device agent**.
These parts work together to provide a secure SSH connection across the network
to Linux-based devices.

## SSH gateway

The ShellHub SSH gateway is a modern SSH server built using the microservices
design pattern, meaning that multiple small, isolated services make up the server.
It must be installed on any cloud provider like Azure, Google, AWS or DigitalOcean.

## Device agent

The ShellHub device agent which must be installed on the device.
