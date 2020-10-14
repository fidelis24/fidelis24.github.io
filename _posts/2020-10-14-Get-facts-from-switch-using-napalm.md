---
layout: post
title: 'Get Facts from Switch Using NAPALM'
---

![Topology](https://raw.githubusercontent.com/fidelis24/img/master/2020-10-14-topology.png)


**get_facts** is just one of the getters that support all NOS or network operating system.
To retrieve facts from a device, in this activity I used NAPALM. NAPALM (Network Automation and Programmability Abstraction Layer with Multivendor) is a Python library that supports several methods to connect to the devices and manipulate configurations or to retrieve data. 


## Installing NAPALM to ubuntu docker or Network Automation docker

apt-get update, to update all references
apt-get install python -y
apt-get install build-essential libssl-dev libffi-dev -y
apt-get install python-pip -y
pip install cryptography
pip install netmiko
pip install napalm



## Python Script to Retrieve Data from the Switch


**from napalm import get_network_driver**  
**driver = get_network_driver('ios')**  
**iosvl2 = driver('192.168.122.202', 'april', 'cisco')**  
**iosvl2.open()**  

**ios_output = iosvl2.get_facts()**  
**print (ios_output)**  


## Configuration on Switch

In order to run the python script well, the switch must have the following configuration:

ip domain-name april.net  
crypto key generate rsa  
1024  

username april privilege 15 password 0 cisco  
enable joie  

 "By default, typing enable takes you to level 15, privileged EXEC mode. In the Cisco IOS, this level is equivalent to having root privileges in UNIX or administrator privileges in Windows. In other words, you have full access to the router." -- **techrepublic.com**
 
## Run the Script 
 
 ![run script getfacts](https://raw.githubusercontent.com/fidelis24/img/master/2020-10-14-runscript.png)

## Troubleshoot Switch
It's a good thing to intentionally make an error to your configuration so you can have better understanding of every single commands you implement in switch or router. Here, I just showed what would happen if we remove the privilege 15 in the switch configuration. 

![with no priv conf](https://raw.githubusercontent.com/fidelis24/img/master/2020-10-14-withnopriv.png)

![with no priv conf results](https://raw.githubusercontent.com/fidelis24/img/master/2020-10-14-withnoprivresult.png)

Just implement again the following command below to make the python script behave well as we run it.

**username april privilege 15 password 0 cisco**




 
> **_NOTE:_**  Hardcoding the password is not a good practice for security purpose. This is just one way to start from scratch if you're new to programming and you iterate from there. Again, I'm April sharing a shared knowledge.

