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
