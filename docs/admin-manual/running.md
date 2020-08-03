ShellHub provides a docker-compose file that will set up and run
everything for you on a single host.

!!! info ""
	Running ShellHub in a multi-host environment with Kubernetes or Docker Swarm is beyond the scope of this guide.

!!! warning ""
	Persistent files are stored by writting files to disk on the host system
	using the Docker's internal volume management. Be warned the downside
	is that files may be hard to locate for tools and applications that
	run directly on the host system. In production environment create a
	data directory on the host system and mount this to a directory visible
	from inside the container. This places the persistent files in a known
	location on the host system, and makes it easy for tools and applications on
	the host system to access the files.

To run ShellHub you can just simply run the up command with docker-compose inside
of ShellHub project dir:

```
docker-compose up -d
```

!!! warning "Be patient, it can take up to 10 minutes for the first time"

When ShellHub server is up and running, you access the Web UI on [http://localhost](http://localhost).

!!! danger "When running in production you should ensure that you enable SSL"
	This is commonly achieved by running Nginx with your certificates on your
	Docker host, service or load balancers in-front of the running container.
