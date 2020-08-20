ShellHub Agent is designed to run on all your systems: physical and virtual servers, even IoT/edge devices.

The best way to install ShellHub Agent is with our automatic one-line installation script, which works with all Linux distributions that have Docker installed and properly set up.

If you want to install ShellHub without Docker you can try to build by yourself or if you are targeting embedded devices checkout our [Yocto Project support layer for ShellHub](https://github.com/shellhub-io/meta-shellhub).

## One-line installation script

!!! info "Docker installed and properly set up on device is required"
	Follow the [Docker Install Instructions](http://docs.docker.com/installation/) for your distro/platform.
	You should always use the latest docker version. The minimum supported Docker version is `18.06`.

Open the ShellHub UI, navigate to _Devices_ on the sidebar, and click on _ADD DEVICE_. It should give you a registration command for installing ShellHub Agent that you need to run on your device:

![Device Register](/img/register-device.png)

After running the command on your device, you'll need to accept the device on the ShellHub UI in order to complete enrollment.
Go to _Devices_ -> _Pending_ locate your device and click _Accept_ button.

After your device is enrolled, it becomes available in _Device List_ page.
