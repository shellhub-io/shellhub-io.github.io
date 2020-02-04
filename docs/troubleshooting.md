If you're having trouble with ShellHub, here are some fixes you can try:

## Cannot start service ssh

!!! error "Error message"
    ERROR: for shellhub_ssh_1  Cannot start service ssh: driver failed programming external connectivity on endpoint shellhub_ssh_1: Error starting userland proxy: listen tcp 0.0.0.0:22: bind: address already in use

If you have getting the error message above when starting up the server using `docker-compose` you have two options to solve this issue:

* Change the OpenSSH daemon port from 22 to whatever on your host machine;
* Change the default SSH gateway port of ShellHub by setting `SHELLHUB_SSH_PORT` variable inside the configuration file.
