ansible-init
============
Server initialization.

Can be run both as `root` and as any other sudoer.  
This will only disable the `root` login if it can connect as a sudoer.

Mandatory configuration
-----------------------
```yaml
# Use this to generate init_user_password_crypted :
# mkpasswd -m sha-512 'PASSWORD' "$(dd if=/dev/urandom bs=1M count=1 2> /dev/null | sha256sum | cut -c -16)"

init_hostname:
init_user_login:
init_user_password_crypted:
init_user_pubkey:  # "ssh-rsa (…)"
```
