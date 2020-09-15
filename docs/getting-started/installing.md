This tutorial will guide you through the steps needed to install and
run a self-hosted instance of ShellHub on your local machine or
on IaaS providers like AWS, Azure, Google Cloud or Digital Ocean.

!!! info "ShellHub Cloud"
	If you prefer to use the cloud hosted service of ShellHub instead of
	self-hosting your own instance, you can skip this step and go to
	[next step](creating-account.md) for creating an account in
	[ShellHub Cloud](https://shellhub.io).

ShellHub is designed using the microservices design pattern, so that multiple small 
and isolated services collaborate to provide the server.
In order to make it easier to test ShellHub and its features, we have created
a Docker Compose environment that brings all of these components up
and connects them together on a single machine.

## System Requirements

Before continuing, make sure:

* Docker Engine and Docker Compose are installed properly.
* Following ports are open: *TCP 80* and *TCP 22*.

## Checkout the latest stable version

First checkout the latest stable version (*{{ shellhub.latest_version }}*) of ShellHub as follows: 

```
git clone -b {{ shellhub.latest_version }} https://github.com/shellhub-io/shellhub.git shellhub
```

Now navigate to ShellHub working directory:

```
cd shellhub
```

## Generate keys

It is required to generate a key pair (private and public) for your ShellHub server instance.

```
./bin/keygen
```

## Running

```
./bin/docker-compose up -d
```

!!! warning "Be patient, it can take up to 10 minutes for the first time"

When ShellHub server is up and running, you access the Web UI on [http://localhost](http://localhost).

!!! danger "When running in production you should ensure that you enable SSL"
	This is commonly achieved by running Nginx with your certificates on your
	Docker host, service or load balancers in-front of the running container.

## Next steps

1. [Creating account](creating-account.md) for creating the initial user
2. [Registering a device](registering-device.md) for registering your first device
3. [Connecting to a device](connecting-device.md) for connecting to your device
