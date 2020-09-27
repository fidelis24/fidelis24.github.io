---
layout: post
title: I just did Telnet..in Network Automation
---

In this blog, I used David Bombal's materials on network automation. Most tutorials are quite short, some are a little bit long. Watching it and doing it myself is really different. I had to troubleshoot some things myself. With the help of people on twitter and people on GNS3 Community, I made it. Though this is just a small step to my journey in network automation but this gave me the AHA! moment. 

![_config.yml]({{ site.baseurl }}/images/092020-1.png)

To get the network automation container, go to [GNS3 marketplace](https://gns3.com/marketplace/appliances) and download it from there. You import it and install the appliance on the GNS3 VM. Just click next then once the network automation is available, you just drag it on the workspace, connect it to the switch like the picture shown. Once the network automtion container is up, you open its console and it will automatically download certain libraries.


Disabling then enabling the network adapters of VMware resolves some of the issues in using the GNS3. This is the thing you should do before you boot the GNS3 if and only if you have just restarted your machine, which in my case I just did. I said should because I came across in a comment section on GNS3 community site and someone had a problem in using GNS3 which solved his problem after the disable and enable things. One of the issues I have solved with disabling and enabling the VM network adapter is that one says -- Cannot connect to compute 'GNS3 VM (GNS3 VM)' with request POST/projects.

![_config.yml]({{ site.baseurl }}/images/2020-09-20-2.png)


It says cannot load the GNS3 settings which is fine and normal since I once disabled the VMware network adapters. At this point, we wait for the GNS3 VM be checked automatically or we can just check it ourselves in Edit > Preferences then on left panel, click on GNS3 VM. On GNS3 preferences, we just check the box to enable the GNS3 VM.

