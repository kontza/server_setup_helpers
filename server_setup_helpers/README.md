# Ansible Collection - kontza.server_setup_helpers

Roles within this collection are common to all my server setups. These roles assume an Ubuntu server or a Debian installation is being worked on.

# Roles

## Generic
This role installs some packages that I previously had always manually installed. An up-to-date list of packages is on the top of the tasks file.

## Ssmtp
This role sets up `ssmtp` for sending out system notification emails via Gmail. You must define a dictionary in your inventory with the following format:
```
notification:
  sender: [the gmail account used for sending the notifications]
  password: [the application password for the sending account]
  recipient: [the default recipient for the notifications]
```

## Autoupdates
This role sets up unattended upgrades. Upgrade period is seven days, and the system will be rebooted at 03:00 regardless of logged in users.
