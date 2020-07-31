In order to use ShellHub, you will need a ShellHub account.

!!! info "ShellHub Cloud"
	If you intended to use [ShellHub Cloud](https://shellhub.io), you can skip this step
	filling the [register form](https://shellhub.io/register).

If you are using ShellHub self-hosted, you need to manually create account running the
`add-user` script from the ShellHub working directory:

```
./bin/add-user <username> <password> <email>
```

!!! warning ""
	In ShellHub self-hosted, each account manage their own fleet of devices. Thus, devices
	registered in one account belongs to their specific namespace and are not
	available in other accounts.
