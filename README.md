server-init
===========
Server initialization.

Can be run both as `root` and as any other sudoer.  
This will only disable the `root` login if it can connect as a sudoer.

**become** is required to run this role.

Mandatory configuration
-----------------------
```yaml
# Use this to generate init_user_password_crypted:
# mkpasswd -m sha-512 'PASSWORD'

init_hostname:
init_user_login:
init_user_password_crypted:
init_user_pubkey:  # "ssh-rsa (…)"
```
