# ROGUE AP WITH HOSTAPD, MAC CHANGE AND SSLSTRIP TRAFFIC CAPTURE 👽

## INTRODUCTION

This script uses _hostapd_, _dnsmasq_, _macchanger_, _sslstrip_ as main programs, and _systemctl_, _iptables_.

I explained every line of the script so anyone is able to understand how a Rogue AP works (it costed me around a week to make things work).

Also I don't take any responsability of any possible harms done with this script.


## CONCEPT

A Rogue AP is a wireless hotspot that let's people connect, but it also performs Man In The Middle attacks.

This way you can sniff every packet ongoing between the user connected to your AP and the router.

This means you can see all the information people (connected to your AP) is sending.

The idea of the MAC change is to make it a little more evasive and remain unknown. :neckbeard:

## INSTALL :arrow_down:

Installation is as simple as:

```
git clone https://github.com/n0nuser/RogueAP.git
```
And `cd` to RogueAP

## USAGE ✋

```
./rogue_ap <ADAPTER 1> <ADAPTER 2> <ESSID>"
```

If it doesn't let you execute it: 'chmod +x rogue_ap' and that's it.

__Arguments explained:__

- ADAPTER 1 : Connected to the network
- ADAPTER 2 : Replicates the signal with ESSID and captures the traffic.
- ESSID     : Name of Rogue AP

It's recommended to select as the second adapter the one with more power and the antenna with more dbi's.

## NOTES 📃

When the program finishes it does a clean up and restores original MAC's.

Also writes a log of HTTPS connections into `log_rogue_ACTUALDATE.log`.

It's also recommended to run Wireshark on second adapter to capture all traffic/packets.
