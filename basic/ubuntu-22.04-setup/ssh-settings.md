# SSH settings

### Config settings

Open `sshd` config and change several parameters

```bash
sudo vim /etc/ssh/sshd_config
```

Useful config options:

```
slogFacility AUTH

PasswordAuthentication no
PermitEmptyPasswords no

X11Forwarding no

PermitRootLogin no # disable root login
AllowUsers dartt0n # list of created users to allow ssh connect
```

