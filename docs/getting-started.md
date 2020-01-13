This tutorial will guide you through the steps needed to install and
run ShellHub on your local computer.

If you are looking for instructions on how to set up ShellHub
for your device fleet on your cloud infrastructure the same steps apply.

## Installing

ShellHub is built using the microservices design pattern, meaning that
multiple small, isolated services make up the server.
In order to make it easy to test ShellHub as a whole, we have created
a Docker Compose environment that brings all of these components up
and connects them together on a single machine.

!!! warning "Before continuing, make sure you have installed Docker Engine and Docker Compose"

In a working directory, download the docker-compose file:

```
$ wget https://raw.githubusercontent.com/shellhub-io/shellhub/master/docker-compose.yml
```

Brings up the ShellHub server:

```
$ docker-compose up -d
```

## Creating the initial user

After ShellHub server have been up and running you need to create the initial user.

Go to the working directory and download the `add-user` utility from our repository:

```
$ wget https://raw.githubusercontent.com/shellhub-io/shellhub/master/bin/add-user
```

Then run the `add-user` utility:

```
$ sh ./add-user <username> <password>
```

## Adding your first device

ShellHub can run in most of any Linux-based operating system with **Docker Engine
installed and running**, no matter what architecture is your device.

The following architectures are supported:

* amd64
* arm32v6
* arm64v8

Open the terminal of your device or access your device with ssh on the local network,
then run the following commands to install the ShellHub agent:

```
$ curl "http://<SERVER_IP>/install.sh?tenant_id=<TENANT_ID>" | sh
```

!!! info ""
    Note that you have to replace `<TENANT_ID>` with your Tenant ID and
    `<SERVER_IP>` with the public IP address of the host that is running
    ShellHub.

## Connecting to your device

ShellHub supports different connection methods:

* Web-based SSH client inside ShellHub UI (Chrome, Firefox)
* Traditional command line SSH client (Linux, Mac OS X)
* Any GUI SSH client like PuTTY (Windows)

Open the ShellHub UI at [http://localhost]() and sign in using the username and password
that was generated in a previous step.

Once you had sign in, go to Device Fleet page ([http://localhost/devices](){target=_blank})
and follow instructions of one method:

### Web-based SSH client

In the Device Fleet page choose the device you want to connect to and click on Terminal icon
located at *Actions* column of the table.

A dialog will show prompting you for the username and password of any existing user in
device's operating system. After providing credentials click on Connect button.

### Command line SSH client

To connect to your device using a command line SSH client you need to know its SSHID address.

In the Device Fleet page choose the device you want to connect to and copy the device's SSHID
address clicking on Copy icon located at SSHID address column of the table.

Run the following command in your terminal:

```
$ ssh <USER>@<SSHID>
```

!!! note ""
    Make sure to replace `<USER>` with existing user in device's operating system and
    `<SSHID>` with the SSHID address copied before.

### PuTTY GUI SSH client

To connect to your device using a GUI SSH client you also need to its SSHID address.

In the Device Fleet page choose the device you want to connect to and copy the device's SSHID
address clicking on Copy icon located at SSHID address column of the table.

Open Putty and fill it out with the following details:

* Host Name (or IP address): `<USER>`@`<SSHID>`
* Port: 22
* Connection type: SSH

!!! note ""
    Make sure to replace `<USER>` with existing user in device's operating system and
    `<SSHID>` with the SSHID address copied before.
