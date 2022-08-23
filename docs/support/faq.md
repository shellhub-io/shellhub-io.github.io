# Frequentely Asked Questions

#### What is ShellHub?
ShellHub is a modern SSH server for remotely accessing Linux devices via CLI or web-based user interface, it avoids the inconvenience such as firewall and NAT when getting your IP address, automating the access process, and helping you easily, seamlessly and securely connect your device to the internet.

#### Does ShellHub support my device?
ShellHub is compatible with Linux devices of any hardware architecture, from single-board computers to desktop, as long as the device has Docker installed.

#### Who should use the ShellHub?
ShellHub is useful for anyone who needs to access their devices safely through a practical and simple process.

#### What ShellHub flavors are available?
ShellHub has two flavors: the ShellHub Open Source and the ShellHub Cloud. And yeah, the Open Source version is fully Free Software and will always be kept that way. We welcome any kind of contribution to our project, so please feel welcome.

#### What is the difference between ShellHub Open Source and ShellHub Cloud version?
ShellHub agent is the same in both versions. The difference resides in features implemented on ShellHub Cloud, which includes technical support, managing firewall rules, session log record, and others that are still under development.

## Installing the ShellHub

#### How do I use ShellHub?
Register yourself on [ShellHub](https://www.shellhub.io/) to create an account. After you've registered, you will be on the dashboard. In dashboard the ```tenant-id``` is available at the top right of the screen and will be used to authenticate your device when it connects to the server.

This identification must be configured inside the agent (ShellHub client) that will be saved in the device along with the image or it must be added as a Docker container.

By default, ShellHub uses [Docker to run the agent](https://shellhub-io.github.io/user-manual/installing/#using-the-one-line-installation-script), but it's possible to install ShellHub from the [source code](https://shellhub-io.github.io/user-manual/installing/#installing-from-the-source-code), or even integrate ShellHub agent into the existing [Yocto Project image](https://shellhub-io.github.io/user-manual/installing/#integrate-with-an-existing-yocto-project-image). Take a look at the tutorial, choose the best for you, and have fun!

#### What knowledge do I need to install ShellHub in my device?
Depending on the installation, different skill sets are needed. ShellHub installation is easy. But if you don't have experience in code, we suggest our [step-by-step using Docker](https://shellhub-io.github.io/getting-started/installing/).

#### Why does ShellHub use Docker?
By default, ShellHub uses Docker to run the agent, which is very convenient, as it provides frictionless addition of devices on the existing system, with Docker support being the only requirement. Docker is also an easy and convenient way to install ShellHub, but not the only one. Please, check the [user manual](https://shellhub-io.github.io/user-manual/) for more.

#### Do I need to have Docker to install the ShellHub agent?
No. It’s possible to install ShellHub from the [source code](https://shellhub-io.github.io/user-manual/installing/#installing-from-the-source-code), or if you use [Yocto Project](https://shellhub-io.github.io/user-manual/installing/#integrate-with-an-existing-yocto-project-image), it’s possible to integrate ShellHub into a ready image. Please check the [user manual](https://shellhub-io.github.io/user-manual/) for more details.

#### I work with low power devices such as RaspberryPi, Thinker Board, and others. Is it possible to install the ShellHub agent on them?
Yes. You can use ShellHub to access virtually any hardware architecture. For low-end devices, take a look at installing from the [source code](https://shellhub-io.github.io/user-manual/installing/#integrate-with-an-existing-yocto-project-image) and integrate with an existing [Yocto Project image](https://shellhub-io.github.io/user-manual/installing/#integrate-with-an-existing-yocto-project-image) documentation sections for ways to do the integration for this kind of device.

## Using the ShellHub

#### My device does not show up in the ShellHub server. What should I do?
First of all, check the internet connection in the device. Then, verify if the device has the Shellhub agent installed. Finally, verify if the device has been accepted on the user interface as it will require manual acceptance to move from the pending state. In case of problems, contact us on [Gitter](https://gitter.im/shellhub-io/community?at=5e30882a6f9d3d3498f5989d).

#### Can I use the ShellHub with Balena?
Yes, just install ShellHub from the [source code](https://shellhub-io.github.io/user-manual/installing/#installing-from-the-source-code).

## ShellHub Server

#### If I use the “docker-compose down” command will I lose my data saved on the server?
Yes. The ```docker-compose down``` command will stop the server and remove containers, networks, volumes, and images created. If you want to use the data stored on this server in the future you must use the ```docker-compose stop``` command that stops executing containers without removing them. To restart them just use ```docker-compose start```. See more in [Docker documentation](https://docs.docker.com/).

#### Can I change the HTTP port used by ShellHub?
Yes, you can access the .env file and overwrite the door setting SHELLHUB_HTTP_PORT.

## Devices

#### How to verify if ShellHub is installed?
Just type ```ps -aux | grep "shellhubio"``` in the device’s terminal e confirm the existence of this process.

#### Is it possible to add automation scripts?
ShellHub is not an automation tool, as its objective is to provide access in an efficient and simple way. However, it can be used together with other tools that provide automatic processes like Ansible, as long as they use the SSH protocol for the connection.

#### Can I use the same ```tenant-id``` on more than one device?
Yes, the ```tenant-id``` is a way of identifying each user's account, being linked directly to it, and not to the device. You can, for example, generate a Yocto Project image with a tenant id for an entire fleet of devices without problems or leave an operating system with the Docker container installed and configured with a given ```tenant-id```.

#### How can I access my device through ShellHub?
Access devices already accepted on the Shellhub server (either Open Source or Cloud) can be done in two ways: on the Devices tab, in the ShellHub server's dashboard, or through the terminal on your workstation, typing user@SSHID (the SSHID is available on dashboard in the Devices tab).

#### Does the device with ShellHub always need a password for the user?

Yes, you need a password. It's part of the tool's configuration and a decision that aims at greater security to access.

#### Can I access HTTP/HTTPS in my device?
Currently, ShellHub doesn’t support other services (HTTP and HTTPS), only SSH.
It’s on our plans to add this kind of feature.

#### As the agent runs inside a container on the device, do I have access to the processes on this device?
Yes. The container runs in the privileged mode, so it’s possible to access the processes of the device normally.

## Security

#### How does ShellHub Cloud guarantee the security of the data accessed?
All data stored by ShellHub is maintained by companies specialized in secure storage in the same places that already guarantees the security of data from the other tools and processes of the [O.S.Systems](https://www.ossystems.com.br).

#### Does ShellHub endanger device security?
No way. ShellHub keeps user passwords and devices encrypted so no one can access them besides the user. The access to devices by the device is done only with the username and password.

#### How can I be sure that ShellHub is safe?
ShellHub is an open source project, so it's open to contributions from the community and available for constant verification of developers and users. That's why open-source projects are considerably safer. And for this reason, ShellHub agent is the same in both versions: Cloud or Open Source.

!!! info "If you have any questions that are not in the FAQ, are having difficulty and want help, or want to exchange some ideas with our team, access our [Gitter](https://gitter.im/shellhub-io/community?at=5e30882a6f9d3d3498f5989d) and we will be happy with your contact."