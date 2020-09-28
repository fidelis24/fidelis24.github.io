---
layout: post
title: 'I just did Telnet..in Network Automation'
---



![](https://github.com/fidelis24/img/blob/master/092020-1.png "Network Automation")

h

In this blog, I used David Bombal's materials on network automation. Most tutorials are quite short, some are a little bit long. Watching it and doing it myself is really different. I had to troubleshoot some things myself. With the help of people on twitter and people on GNS3 Community, I made it. Though this is just a small step to my journey in network automation but this gave me the AHA! moment. 


To get the network automation container, go to [GNS3 marketplace](https://gns3.com/marketplace/appliances) and download it from there. You import it and install the appliance on the GNS3 VM. Just click next then once the network automation is available, you just drag it on the workspace, connect it to the switch like the picture shown. Once the network automation container is up, you open its console and it will automatically download certain libraries.


Disabling then enabling the network adapters of VMware resolves some of the issues in using the GNS3. This is the thing you should do before you boot the GNS3 if and only if you have just restarted your machine, which in my case I just did. I said should because I came across in a comment section on GNS3 community site and someone had a problem in using GNS3 which solved his problem after the disable and enable things. One of the issues I have solved with disabling and enabling the VM network adapter is that one says -- Cannot connect to compute 'GNS3 VM (GNS3 VM)' with request POST/projects.


![](/img/2020-09-20-2.png?raw=true)

It says cannot load the GNS3 settings which is fine and normal since I once disabled the VMware network adapters. At this point, we wait for the GNS3 VM be checked automatically or we can just check it ourselves in Edit > Preferences then on left panel, click on GNS3 VM. On GNS3 preferences, we just check the box to enable the GNS3 VM.


And for another prompt that says 'Timeout after 5 seconds for request http://admin@localhost:3080/v2/version. Please check the connection is not blocked by a firewall or an anti-virus.', make sure to deactivate any of antivirus installed on your PC.
If the GNS3 isn't behaving well, you can close it and just boot it again.


## script on network automation container
 	
~~~python
import getpass  
import telnetlib  

HOST = '192.168.122.202'

password = getpass.getpass()

tn = telnetlib.Telnet(HOST)

tn.read_until(b"Username: ")
tn.write(user.encode('ascii') + b"\n")
if password:
    tn.read_until(b"Password: ")
    tn.write(password.encode('ascii') + b"\n")
    
tn.read(b"enable\n")

tn.write(b"joie\n")
tn.write(b"conf t\n")
tn.write(b"vlan 2\n")
tn.write(b"name python_vlan2\n")
tn.write(b"vlan 3\n")
tn.write(b"name vlan3py\n")
tn.write(b"end\n")
tn.write(b"copy run start\n")
tn.write(b"\n")
tn.write(b"exit\n")

print(tn.read_all().decode('ascii'))
 	
~~~ 


## Configuration on Network Automation Container

Uncomment the two lines under dhcp config for eth0
This device would receive ip address from the NAT node or NAT cloud.
Type 'ifconfig' and see the ip address received.
Mine is 192.168.122.101.

## Configuration on switch CiscoIosvl2
~~~shell
int vlan 1

ip add 192.168.122.202 255.255.255.0


username april password cisco

enable password joie

~~~


Make sure the ip address you typed in your vlan 1 is within the network range and subnet of the network automation container have received. 

This is where my humble journey in world of network automation begins. With just few lines of code, you can push a configuration to a router or switch.
  



