# Upgrade to Enterprise

This section describes how to upgrade from the ShellHub Community Edition to the ShellHub Enterprise.

## Prerequisites

To complete this guide you will need:

* An [O.S. Systems](https://ossystems.com.br) Docker Registry account to pull ShellHub Enterprise containers.
* A valid ShellHub Enterprise license file.

!!! info "[Contact us](mailto:contato@ossystems.com.br) to get a quote for the Enterprise version"

## Configuring Enterprise

Once the Open Source containers of the ShellHub are up and running, let's configure your environment
to bring up the ShellHub Enterprise containers.

### Pull ShellHub Enterprise containers

First log in to the [O.S. Systems](https://ossystems.com.br) docker registry with your ShellHub Enterprise credentials:

```
docker login docker-registry.ossystems.com.br
```

### Update environment config

Open the `.env.override` file inside ShellHub project dir and set the following variables:
 
* `SHELLHUB_ENTERPRISE=true`
* `SHELLHUB_ENTERPRISE_ADMIN_USERNAME=<user>`
* `SHELLHUB_ENTERPRISE_ADMIN_PASSWORD=<password>`

!!!warning "Make sure to replace `<user>` and `<password>` with your own values."

## Restart containers

If ShellHub is up and running you need to restart containers by running:

```
./bin/docker-compose stop
./bin/docker-compose up -d
```
