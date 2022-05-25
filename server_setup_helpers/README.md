# Ansible Collection - kontza.server_setup_helpers

Roles within this collection are common to all my server setups. These roles assume the following:
- A MicroOS server with a non-root user who can log in with SSH keys.
- Python 3 installed. This is better to be installed post system install, but before Ansible run, as the first transactional pkg install creates the required file for Ansible's install to detect that the system is a transactional system.

# Roles

## Generic
This role installs some packages that I previously had always manually installed. An up-to-date list of packages is on the top of the tasks file. **Note!** This also installs packages required by other roles.

## Msmtp
This role sets up `msmtp` for sending out system notification emails via Gmail. You must define a dictionary in your inventory with the following format:
```
notification:
  sender: [the gmail account used for sending the notifications]
  password: [the application password for the sending account]
  recipient: [the default recipient for the notifications]
```
