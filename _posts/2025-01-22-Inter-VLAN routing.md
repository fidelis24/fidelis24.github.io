---
layout: post
title: 'Inter-VLAN Routing'
---

![Inter-Vlan Routing](https://raw.githubusercontent.com/fidelis24/img/master/2025-01-22-InterVlan.png)


**Inter-VLAN Routing**   means routing the traffic between VLANS. It makes different VLANs to communicate with each other improving the security and organization of a network.
  

## Training the device to learn two routhing methods  
  
![rip-ospf-router](https://raw.githubusercontent.com/fidelis24/img/master/rip-ospf-router.png)  

We need to implement the following syntax on the router to train the following routes to learn another  
routing method. On RIP, we redistribute the RIP routes into OSPF. On OSPF, we redistribute the OSPF route      
into RIP.  
  

## Verification of Route Redistribution Between the Two Routes  
  
### OSPF Router  
![!ospf-router](https://raw.githubusercontent.com/fidelis24/img/master/ospf-router.png)  
  
As seen on the figure above, the OSPF router have just learned the other routes. The OSPF router have now added   10.0.0.0/8 and 192.168.100.0/24 networks into its routing method.  

The command **redistribute rip metric 1** introduces the OSPF routes into the RIP method.  
  
      
### RIP Router  
![rip-router](https://raw.githubusercontent.com/fidelis24/img/master/rip-router.png)  
Based on the figure above, besides the networks 192.168.100.0/24 and 10.0.0.0/8, the  
other networks have just been added through the RIP routing method.  
     
The command **redistribute ospf 1 metric 1** introduces the RIP routes into the OSPF method.  

## Configuration on the devices  

Take a closer look of the topology by clicking the link below:

([pkt here](https://github.com/fidelis24/route-redistribution-ospf-and-rip/raw/main/Route-redistribution-ospf-and-rip.pkt))  
 



  
  