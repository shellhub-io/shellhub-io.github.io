This tutorial will guide you through the steps needed to install and
run ShellHub.

!!! info ""
    If you are looking for instructions on how to set up ShellHub for
    your device fleet on your cloud infrastructure the same steps apply.

A hosted version of ShellHub is available at https://shellhub.io/.

ShellHub is designed using the microservices design pattern, so that multiple small 
and isolated services collaborate to provide the server.
In order to make it easier to test ShellHub and its features, we have created
a Docker Compose environment that brings all of these components up
and connects them together on a single machine.

!!! warning "Before continuing, make sure you have installed Docker Engine and Docker Compose"

In a working directory, clone the ShellHub repository:

```
git clone -b {{ shellhub.latest_version }} https://github.com/shellhub-io/shellhub.git shellhub-{{ shellhub.latest_version }}
```

```
cd shellhub-{{ shellhub.latest_version }}
```

## Generate keys

It is required to generate a key pair (private and public) for your ShellHub server instance.

```
./bin/keygen
```

## Running

```
docker-compose up -d
```

!!! warning "Be patient, it can take up to 10 minutes for the first time"

When ShellHub server is up and running, you access the Web UI on [http://localhost](http://localhost).

## Next steps

1. [Adding account](guides/adding-account.md) for creating the initial user
2. [Registering a device](guides/registering-device.md) for registering your first device
3. [Connecting to a device](guides/connecting-device.md) for connecting to your device
