This tutorial will guide you through the steps needed to install and
run ShellHub.

If you are looking for instructions on how to set up ShellHub
for your device fleet on your cloud infrastructure the same steps apply.

## Installing

ShellHub is designed using the microservices design pattern, so that multiple small 
and isolated services collaborate to provide the server.
In order to make it easier to test ShellHub and its features, we have created
a Docker Compose environment that brings all of these components up
and connects them together on a single machine.

!!! warning "Before continuing, make sure you have installed Docker Engine and Docker Compose"

In a working directory, clone the ShellHub repository:

```
git clone -b v0.0.1 https://github.com/shellhub-io/shellhub.git shellhub-v0.0.1
```

```
cd shellhub-v0.0.1
```

### Generate keys

It is required to generate a key pair (private and public) for your ShellHub server instance.

```
./bin/keygen
```

### Starting

For bringing up the ShellHub server, run:

```
docker-compose up -d
```

!!! warning "Make sure ports 80 and 22 are available at the host end"

## Creating the initial user

As the ShellHub server is up and running, you need to create the first user.

```
./bin/add-user <username> <password>
```

!!! info "You should keep the _Tenant ID_ from the command output"

## Adding your first device

To add a device to ShellHub you need to install ShellHub Agent onto it.

The ShellHub Agent runs inside a Docker container. Make sure you have Docker
installed and properly set up.

Open a terminal on your device and then run the following commands to install the ShellHub agent:

```
curl "http://<SERVER_IP>/install.sh?tenant_id=<TENANT_ID>" | sh
```

!!! info ""
    Replace `<TENANT_ID>` with your _Tenant ID_ and
    `<SERVER_IP>` with the public IP address of the host running
    ShellHub.

## Connecting to your device

ShellHub provides different connection methods:

* Web-based SSH client within the ShellHub UI (Chrome, Firefox)
* Traditional command line SSH client (Linux, Mac OS X)
* Any GUI SSH client like PuTTY (Windows)

Open the ShellHub UI at [http://localhost]() and sign in using the username and password
generated previously.

Once you are logged in, go to the _Device Fleet_ page ([http://localhost/devices](){target=_blank})
and follow instructions for a supported connection alternative:

### Web-based SSH client

In the _Device Fleet_ page, choose the device you wish to connect to and click on _Terminal_ icon
located at the *Actions* column on the chart.

A dialog will pop up prompting you for the username and password of an existing user on the
device's operating system. After providing credentials, click on _Connect_ button.

### Command line SSH client

To connect to your device using a command line SSH client, you need to know its SSHID address.

In the _Device Fleet_ page, choose the device you want to connect to and copy the device's SSHID
address clicking on _Copy_ icon located on SSHID address column of the chart.

Then, run the following command on your terminal:

```
ssh <USER>@<SSHID>
```

!!! note ""
    Make sure to replace `<USER>` with the existing user on the device's operating system and
    `<SSHID>` with the aforementioned SSHID address.

### PuTTY GUI SSH client

Connecting to your device using a GUI SSH client also requires its SSHID address.

In the _Device Fleet_ page, choose the device you want to connect to and copy the device's SSHID
address by clicking on the _Copy_ icon located at SSHID address column on the table.

Open Putty and fill in with the following information:

* Host Name (or IP address): `<USER>`@`<SSHID>`
* Port: 22
* Connection type: SSH

!!! note ""
    Make sure to replace `<USER>` with the existing user on the device's operating system and
    `<SSHID>` with the aforementioned SSHID address.
