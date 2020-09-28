---
layout: post
title: 'Keep the Network Secured Within'
---


![Keep Network Secured](https://raw.githubusercontent.com/fidelis24/img/master/2020-09-24-good-user.png)


In response to my CCNA journey in section of Security Fundamentals, I set up a simple topology on Packet Tracer and make sure I can ping the router from the PC0 but not from PC1. I assume the PC1 as a Kali Linux user as someone who would do a mac overflow attack in the switch. Port-security is the countermeasure for MAC address table overflow attack. The administrator can limit the number of mac addresses allowed per ports on the switch, thus protects the network from the said attack.

 ([pkt Here](https://github.com/fidelis24/port-security_to_protect_the_network_within/raw/master/Port-security_to_Protect_the_network_within.pkt
))

## Let's use the bad PC user

If the device or host that isn't manually configured or have sticked it's MAC address to the port security configuration, then it won't be able to attack the network.

![Network Not Secured](https://raw.githubusercontent.com/fidelis24/img/master/2020-09-24-baduser.png)

## For the switch to come back up..

Using the 'shutdown' or 'sh' and 'no shutdown' or 'no sh' commands under the interface f0/1 will make the port transition from error-disabled state.

## Port-Security Configuration

![portsecurity](https://raw.githubusercontent.com/fidelis24/img/master/2020-09-24-switchportconfig.png)
