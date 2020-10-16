# Upgrade to Enterprise

This section describes how to upgrade from the ShellHub Open Source to the ShellHub Enterprise.

## Configuring Enterprise

Once the Open Source containers of the ShellHub are up and running, let's configure your environment
to bring up the ShellHub Enterprise containers.

### Pull ShellHub Enterprise containers

First log in to the [O.S. Systems](https://ossystems.com.br) docker registry with your ShellHub Enterprise credentials:

```
docker login docker-registry.ossystems.com.br
```

!!! info "If you have lost your credentials or need an evaluation account please [email us](mailto:contato@ossystems.com.br)."

### Update environment config

Open the `.env.override` file inside ShellHub project dir and set the following variables:
 
* `SHELLHUB_ENTERPRISE=true`
* `SHELLHUB_ENTERPRISE_ADMIN_USER=<user>`
* `SHELLHUB_ENTERPRISE_ADMIN_PASSWORD=<password>`

!!!warning "Make sure to replace `<user>` and `<password>` with your own values."

## Restart containers

If ShellHub is up and running you need to restart containers by running:

```
./bin/docker-compose stop
./bin/docker-compose up -d
```
