---
layout: post
title: 'Inter-VLAN Routing just try'
---

![!Inter-Vlan Routing](https://raw.githubusercontent.com/fidelis24/img/master/2025-01-22-InterVlan.png)


**Inter-VLAN Routing**   means routing the traffic between VLANS. It makes different VLANs to communicate with each other improving the security and organization of a network.
  

## Ping the PC from other VLAN 
  
![!ping](https://raw.githubusercontent.com/fidelis24/img/master/pingfrompc0-topc2.png)  

Regardless of difference on network, the PC0 which has an IP address of 192.168.10.11, it can reach or communicate with the PC2 which has an IP address of 192.168.25.86.
  

## Removing the VLAN 25 from Switch 2  
  
 
![!novlan25](https://raw.githubusercontent.com/fidelis24/img/master/novlan25.png)  
  
As seen on the figure above, after implementing the "no vlan 25" on global configuration mode, the PC0 cannot reach the PC2 anymore. However, the PC0 can still reach the PC1 which is on the same VLAN as PC0.

  
  