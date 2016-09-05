server-init
===========
Server initialization.

Can be run both as `root` and as any other sudoer.  
This will only disable the `root` login if it can connect as a sudoer.

**become** is required to run this role.

Configuration
-------------
## Mandatory
```yaml
# Use this to generate init_user_password_crypted:
# mkpasswd -m sha-512 'PASSWORD'

init_hostname:
init_user_login:
init_user_password_crypted:
init_user_pubkey:  # "ssh-rsa (…)"
```

## Optional
```yaml
# boolean, should we disable support for ipv6 inside ufw
init_disable_ufw_ipv6:

# Ports en open, eg.:
init_ufw_open:
  - to_port: 80
    proto: "tcp"

# Files to write, eg.:
init_files:
  - content="foo"
    dest="/bar"
    owner="root"
    group="root"
    mode="0600"
```
