<h1> Secondary bind9 dns server</h1>

 

<h2>Description</h2>
 In this project, I add a secondary DNS server to an existing topology for network redundancy.
<br />


<h2></h2>

<h2>Environments and programs used </h2>

- <b>Cisco CML 2.8</b> 

- <b>Cisco cli</b>

- <b>Ubuntu terminal</b>

<h2>Program walk-through:</h2>

<p align="center">
Topology in use <br/>
 <br />
<img src= "images/topology 1.PNG" height="80%" width="80%"/>
 <br />
 The topology we are using has two subnets, an inside interface, and a DMZ connected to 
 An ASA firewall is connected to the outside network.<br/>
<br />
<br />
Install updates<br/>
 <br />
<img src="images/install-files 1.PNG" height="80%" width="80%"/>
 <br />
  Update Ubuntu using sudo apt-get update before installing bind9.<br />
<br />
<br />
Install bind9<br/>
 <br />
<img src="images/named.conf.options 3.PNG" height="80%" width="80%" />
<br />
<br/>
named.conf.options 
 <br />
<img src="images/named.conf.options-secondary.PNG" height="80%" width="80%" />
<br />
Set up the named.conf.options file with an ACL so that only permitted clients can access this
DNS server. This is also where we allow queries and set up forwarders. This file 
 will be set up similarly to the master server.<br />
<br />
<br />
named-checkconf
 <br />
<img src="images/check-conf 5.PNG" height="80%" width="80%" />
 <br />
 To check the syntax of our files, use named-checkconf followed by the 
file name.<br />
<br />
<br />
Declare zones on secondary dns <br/>
 <br />
<img src="images/name.conf.local-slave 4.PNG" height="80%" width="80%" />
 <br />
 Here, we have to tell the secondary server where to find the updates for
 The zone, so we have to tell it what the primary IP is and what the file name is
 on the primary server.<br />
<br />
<br />
 Zone transfer from primary server<br/>
 <br />
<img src="images/named.conf.local-master 2.PNG" height="80%" width="80%" />
 <br />
 We have to tell the primary server the address of the secondary server so it knows 
 where to send the copy of the zone file. I'm also going to allow the primary server to
 notify the secondary server when changes happen. <br />
<br />
<br />
Test functionality <br/>
 <br />
 <img src="images/remote-client-test 8.PNG" height="80%" width="80%" />
 <br />
Finally, on a client pc, change the nameserver in the netplan file to use only the secondary
 server. I can resolve domain names from my zone, so it is working.<br />
<br />
<br />
<p/>

