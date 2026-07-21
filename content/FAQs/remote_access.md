---
title: Remote Access to SCOREC
---

If you are not connected to the RPI network you can access the SCOREC network
with and without the RPI VPN enabled.

## With the VPN

Use the RPI VPN (see
https://itssc.rpi.edu/hc/en-us/sections/360001746371-VPN-Connection-and-Installation) and then connect to `jumpgate.scorec.rpi.edu` via `ssh`.

## Without the VPN

`ssh` to `jumpgate-mfa.scorec.rpi.edu` - you will be prompted for your RCS ID
and password and then need to use DUO for a second factor.

