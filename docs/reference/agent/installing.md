We offer different ways to install the ShellHub Agent. The easiest way is with our [one-line installation script](#using-the-one-line-installation-script), which works with all major Linux distributions but it requires that you have Docker installed and properly set up.

If you want to install ShellHub Agent but would like to not use Docker, currently we have two other options:

1. [Install the ShellHub Agent from the source code](#installing-from-the-source-code),
1. [Integrate the ShellHub Agent into an existing Yocto Project image](#integrate-with-an-existing-yocto-project-image)

In next sessions we'll cover each of these alternatives.

## Using the One-line installation script

!!! info "Prerequisites"
	Docker installed and properly set up on device is required.
	Follow the [Docker Install Instructions](http://docs.docker.com/installation/) for your distro/platform.
	You should always use the latest docker version. The minimum supported Docker version is `18.06`.

Open the ShellHub UI, navigate to _Devices_ on the sidebar, and click on _ADD DEVICE_. It should give you a registration command for installing ShellHub Agent that you need to run on your device:

![Device Register](/img/register-device.png)

## Installing from the source code

!!! info "Prerequisites"
	ShellHub Agent requires Go 1.14 to compile, please refer to the [official documentation](https://golang.org/doc/install) for how to install Go in your system.

First checkout the latest stable version (*{{ shellhub.latest_version }}*) of ShellHub as follows: 

```
git clone -b {{ shellhub.latest_version }} https://github.com/shellhub-io/shellhub.git shellhub
```

Next, we need to execute the following command to build ShellHub Agent:

```
cd shellhub/agent
go build
```

Use `file ./agent` to check if executable was built.

## Integrate with an existing Yocto Project image

To use ShellHub in a Yocto Project image is necessary to add [meta-shellhub](https://github.com/shellhub-io/meta-shellhub) layer in your project.

```
git clone git@github.com:shellhub-io/meta-shellhub.git
```

!!! info ""
	ShellHub have support to Dunfell(master), [Zeus](https://github.com/shellhub-io/meta-shellhub/tree/zeus), [Sumo](https://github.com/shellhub-io/meta-shellhub/tree/sumo) and [Rocko](https://github.com/shellhub-io/meta-shellhub/tree/rocko) branches.

Besides that, add the settings below in your local.conf file:

```
CORE_IMAGE_EXTRA_INSTALL += "packagegroup-shellhub-runtime"
SHELLHUB_TENANT_ID = "<your tenant id here>"
```

`CORE_IMAGE_EXTRA_INSTALL`: this variable will install the ShellHub agent in your device.

`SHELLHUB_TENANT_ID`: needs to be filled with your *tenant code* available in the ShellHub platform at the top right in icon with the user name.

Remember to add the other configurations according to your needs. After this, just generate the desired image.

!!! attention ""
	Stay tuned to the fact that ShellHub demands the use of a password in the device will use ShellHub.
