ShellHub provides flexible firewall for filtering SSH connections.
It gives a fine-grained control over which SSH connections reach the devices.

Using firewall rules you can deny or allow SSH connections to your devices based on a configuratio that you specify.

!!! info "NOTE"
	This feature is only available in [ShellHub Cloud](https://shellhub.io).

## Firewall rule parameters

Each firewall rule has a priority number which is evaluated in ascending order
(starting with the lowest). It's makes a lot easier to manage a large number
of firewall rules.

A firewall rule is composed of the following parameters:

* **Active**: Indicates if the rule is active
* **Priority**: The rule's priority
* **Action**: Firewall action to perform (allow or deny)
* **Source IP**: Incoming connection's source IP address (regexp format)
* **Username**: Incoming connection's target username (regexp format)
* **Hostname**: Incoming connection's target device's hostname (regexp format)

!!! warning "Pay attention"
    The following parameters has support for regular expression: `Source IP`, `Username`, `Hostname`.
    Make sure to escape the periods in the value of these parameters.
