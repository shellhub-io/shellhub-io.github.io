ShellHub is easy to configure, all configuration is done via environment
variables inside the `.env.override` file located at the root of ShellHub project dir.

## Environment Variables

### :arrow_right: `SHELLHUB_HTTP_PORT`

The HTTP listen port for the ShellHub web-based GUI, API and Reverse SSH tunnel.

Default: 80

### :arrow_right: `SHELLHUB_HTTPS_PORT`

The HTTPS listen port for the ShellHub web-based GUI, API and Reverse SSH tunnel.

Default: 443

### :arrow_right: `SHELLHUB_SSH_PORT`

The SSH listen port for incoming SSH connections to devices.

Default: 22

### :arrow_right: `SHELLHUB_PROXY`

Set this variable to `true` if you are running a Layer 4 load balancer with proxy protocol in front of ShellHub.

Default: false

### :arrow_right: `SHELLHUB_AUTO_SSL`

Automatic HTTPS with Let's Encrypt

Default: false

### :arrow_right: `SHELLHUB_REDIRECT_TO_HTTPS`

Redirect requests from HTTP port to HTTPS port

!!! info ""
	In order to enable HTTPS redirection, you need to have HTTPS enabled

Default: true

### :arrow_right: `SHELLHUB_DOMAIN`

Domain of the server

!!! info ""
	Only required if automatic HTTPS is enabled

Default: localhost
