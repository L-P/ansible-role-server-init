# server-init
Server initialization, install basic packages, setup basic security stuff and
create _ansible_ user.

This role can be run both as `root` and as any other sudoer.  
This will only disable the `root` login if it can connect as a sudoer.

## Requirements
Role created for Ubuntu 16.04 amd64 and armhf.  
**become** is required to run this role.

## Role Variables
### Mandatory
```yaml
# Use this to generate init_user_password_crypted:
# mkpasswd -m sha-512 'PASSWORD'

init_hostname:
init_user_login:
init_user_password_crypted:
init_user_pubkey:  # "ssh-rsa (…)"
```

### Optional
```yaml
# boolean, should we disable ufw ipv6 support, this is needed on some armhf hosts.
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

## Dependencies
None.

## Example Playbook
```yaml
- hosts: all
  become: true
  roles:
    - {role: L-P.server-init}
```

## License
MIT
