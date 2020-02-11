Frequently Asked Questions
==========================
How can I get the SSHID from my device?
--------------------------------------
From your device execute the following command on your shell:

`docker  exec  shellhub agent info`

this returns your device's  SSHID inside a json
#### example
```
{
    "sshid": "namespace.device_name@address"
}
```

