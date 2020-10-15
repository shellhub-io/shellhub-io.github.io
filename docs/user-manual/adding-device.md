Before beginning, you need to have the ShellHub account because the ```TENANT_ID``` only is generated and will stay available with an account. You will need this information in settings on the device. In case you don't have an account yet, access ShellHub platform, and register yourself.

Now you must put the ShellHub agent in a device. The agent can be added in a device for three ways like shown in **Instaling**: with [Docker](/reference/agent/installing#using-the-one-line-installation-script), [manually](/reference/agent/installing#installing-from-the-source-code), or in a [Yocto Project image](/reference/agent/installing#integrate-with-an-existing-yocto-project-image).

After install the ShellHub agent on your device, you'll need to accept the device on the ShellHub UI in order to complete enrollment.
Go to **Devices** -> **Pending** locate your device and click **Accept** button.

![Device Pending](/img/pending-device.png)

After your device is enrolled, it becomes available in Device List page.
