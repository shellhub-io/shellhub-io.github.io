For production deployment, there are a few things to modified to make sure
your deployment is ready for production usage.

!!! info "Override Docker Compose configuration"
	You can use `docker-compose.override.yml` file to override different
	aspects of your deployment instead of editing `docker-compose.yml` directly
	in order to avoid conflict with upstream code.

## Where to store persistent files

### Default setup

By default, persistent files are stored by writting files to disk on the host system
using the Docker's internal volume management.

!!! warning "Be warned"
	The downside is that files may be hard to locate for tools and
	applications that run directly on the host system.

### Production setup

In production environment create a data directory on the host system
and mount this to a directory visible from inside the container.

!!! success "Recommended for production"
	This places the persistent files in a known location on the host system,
	and makes it easy for tools and applications on the host system to access the files.

To achieve this, put the following in the `docker-compose.override.yml` file inside
ShellHub project dir:

```yaml
version: '3.7'
services:
  mongo:
	volumes:
      - /usr/local/mongo/data:/data/db
```

!!! warning ""
	Make sure `/usr/local/mongo/data` directory exists on the host.

## Enable SSL

!!! danger "When running in production you should ensure that you enable SSL"

This is commonly achieved by running Nginx with your certificates on your
Docker host, service or load balancers in-front of the running container.

!!! info "Don't forget to set [`SHELLHUB_PROXY`](/admin-manual/configuring/#shellhub_proxy) environment when putting a Layer 4 load balancer with proxy protocol in-front of ShellHub."
