Before beginning, you need to have the ShellHub account because the TENANT_ID only is generated and will stay available with an account. You will need this information in settings before generating the image. In case you don't have an account yet, access [ShellHub platform](https://cloud.shellhub.io/login) and register yourself.

To use ShellHub in a Yocto Project image is necessary to add [meta-shellhub](https://github.com/shellhub-io/meta-shellhub) layer in your project.

```
git clone git@github.com:shellhub-io/meta-shellhub.git
```

!!! info ""
	ShellHub have support to Dunfell(master), [Zeus](https://github.com/shellhub-io/meta-shellhub/tree/zeus), [Sumo](https://github.com/shellhub-io/meta-shellhub/tree/sumo) and [Rocko](https://github.com/shellhub-io/meta-shellhub/tree/rocko) branches.

Besides that, add the settings below in your local.conf file:

```
CORE_IMAGE_EXTRA_INSTALL += "packagegroup-shellhub-runtime"
SHELLHUB_TENANT_ID = ""
```

CORE_IMAGE_EXTRA_INSTALL: this variable will install the ShellHub agent in your device.

SHELLHUB_TENANT_ID: needs to be filled with your tenant code available in your account such as shown below:

![](/img/yocto-tenant.gif)

Remember to add the other configurations according to your needs. After this, just generate the desired image.

!!! attention ""
	Stay tuned to the fact that ShellHub demands the use of a password in the device will use ShellHub.
