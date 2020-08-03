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

