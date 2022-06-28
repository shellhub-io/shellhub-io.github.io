ShellHub provides different connection methods:

* Web-based SSH client within the ShellHub UI (Chrome, Firefox)
* Traditional command line SSH client (Linux, Mac OS X)
* Any GUI SSH client like PuTTY (Windows)

Open the ShellHub UI and login using a valid account credentials.

Once you are logged in, navigate _Devices_ on the sidebar and follow instructions for a supported connection method:

### Web-based SSH client

In the _Devices_ page, choose the device you wish to connect to and click on terminal icon at the row. A dialog will pop up prompting you for the username and password of an existing user on the
device's operating system. After providing credentials, click on _Connect_ button.

### Command line SSH client

To connect to your device using a command line SSH client, you need to know its `SSHID` address.

In the _Devices_ page, choose the device you want to connect to and
copy the device's `SSHID` address.

Then, run the following command on your terminal:

```
ssh <USER>@<SSHID>
```

!!! note ""
    Make sure to replace `<USER>` with the existing user on the device's operating system and
    `<SSHID>` with the SSHID copied before.
!!! warning ""
    `<SSHID>` is composed of `<device name>@<server address>`. The server address has an additional @, characteristic of ShellHub syntax.
    
### PuTTY GUI SSH client

Connecting to your device using a GUI SSH client also requires its `SSHID` address.

In the _Devices_ page, choose the device you want to connect to and
copy the device's `SSHID` address.

Open Putty and fill in with the following information:

* Host Name (or IP address): `<USER>`@`<SSHID>`
* Port: 22
* Connection type: SSH

!!! note ""
    Make sure to replace `<USER>` with the existing user on the device's operating system and
    `<SSHID>` with the SSHID copied before.
