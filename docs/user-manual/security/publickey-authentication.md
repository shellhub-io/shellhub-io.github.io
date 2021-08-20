Public key authentication is a way of logging into an devices using a cryptographic key rather than a password which is the default method most SSH clients use to authenticate with remote devices, but it suffers from potential security vulnerabilities like brute-force login attempts.

Using key-based authentication offers a range of benefits:

* Allow multiple developers to log in as the same system user without having to share a single password between them;
* Revoke a single developer's access without revoking access by other developers; and
* Make it easier for a single developer to log in to many accounts without needing to manage many different passwords.
