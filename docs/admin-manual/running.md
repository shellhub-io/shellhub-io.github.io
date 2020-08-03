```
docker-compose up -d
```

!!! warning "Be patient, it can take up to 10 minutes for the first time"

When ShellHub server is up and running, you access the Web UI on [http://localhost](http://localhost).

!!! danger "When running in production you should ensure that you enable SSL"
	This is commonly achieved by running Nginx with your certificates on your
	Docker host, service or load balancers in-front of the running container.
