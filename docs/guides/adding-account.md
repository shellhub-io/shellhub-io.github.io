The web interface requires you log in with a valid username and password.

!!! warning "Before continuing, make sure you have installed uuidgen"

To add a user account, you must run the `add-user` script from the ShellHub working directory:

```
./bin/add-user <username> <password>
```

In ShellHub, each account manage their own fleet of devices. Thus, devices
registered in one account belongs to their specific namespace and are not available
in other accounts.
