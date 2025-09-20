# plan9srv-systemd-units
Systemd units for Plan 9 services

## Installation

```sh
makepkg -si
```

## Setup

```sh
run0 systemctl enable --now secstored.service

systemctl --user enable --now fontsrv.service plumber.service factotum.service
```

### factotum

If there is your factotum keys in secstored, you can setup factotum to load these keys automatically.

First, you can store your password for secstored into **secstore.txt**. Then it will be encrypted to **secstore.key** with below:

```sh
systemd-creds --user --name=secstore.secret encrypt secstore.txt ~/lib/secstore.key
rm secstore.txt
```

Finally, you add LoadCredentialEncrypted to **factotum.service** unit to load **secstore.key**.

```sh
systemctl --user edit factotum.service
```

For instance:

```ini
[Service]
LoadCredentialEncrypted=secstore.secret:%h/lib/secstore.key
ExecStartPost=bash -c 'secstore -iG factotum <%d/secstore.secret | 9p write -l factotum/ctl'
```
