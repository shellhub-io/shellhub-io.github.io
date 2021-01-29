ShellHub comes with a useful scripts for managing a self-hosted ShellHub instance.
These scripts are located in `bin` of ShellHub project dir.

!!! info "ShellHub Enterprise"

	If you are managing a ShellHub Enterprise self-hosted instance,
	all administrative tasks can be performed via the [Admin Console](/admin-manual/admin-console.md).

Each script must be run from the root of ShellHub project dir.

## Scripts

### Namespace scripts

#### :arrow_right: `add-namespace`

Add namespace to a local running instance of ShellHub.

<strong> Usage: </strong>`./bin/add-namespace <namespace> <owner>`

#### :arrow_right: `del-namespace`

Delete namespace to a local running instance of ShellHub.

<strong> Usage: </strong>`./bin/del-namespace <namespace>`

#### :arrow_right: `add-user-namespace`

Add user to specific namespace to a local running instance of ShellHub.

<strong> Usage: </strong>`./bin/add-user-namespace <username> <namespace>`

#### :arrow_right: `del-user-namespace`

Delete user from a specific namespace to a local running instance of ShellHub.

<strong> Usage: </strong>`./bin/del-user-namespace <username> <namespace>`

### User scripts

#### :arrow_right: `add-user`

Add user account to a local running instance of ShellHub.

<strong> Usage: </strong>`./bin/add-user <username> <password> <email>`

#### :arrow_right: `del-user`

Delete user account from a local running instance of ShellHub.

<strong> Usage: </strong>`./bin/del-user <username>`

#### :arrow_right: `reset-user-password`

Reset user account password from a local running instance of ShellHub.

<strong>Usage:</strong> `./bin/reset-user-password <username> <password>`

### Key generation scripts

#### :arrow_right: `keygen`

Generate a key pair (private and public) for ShellHub self-hosted instance.

<strong> Usage: </strong>`./bin/keygen`
