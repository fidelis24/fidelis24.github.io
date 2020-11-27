---
layout: post
title: 'Route Redistribution'
---

![route-redistribution](https://raw.githubusercontent.com/fidelis24/img/master/route-redistribution.png)


**Route redistribution** is the act of redistribution of the routes learned by a routing method  
to a different routing method.    
  

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
 ([pkt Here](https://github.com/fidelis24/port-security_to_protect_the_network_within/raw/master/Port-security_to_Protect_the_network_within.pkt))




  
  