<h1> Secondary bind9 dns server</h1>

 

<h2>Description</h2>
 In this project I add a secondary dns server to an existing topology for network redundency.
<br />


<h2></h2>

<h2>Environments and programs used </h2>

- <b>Cisco CML 2.8</b> 

- <b>Cisco cli</b>

- <b>Ubuntu terminal</b>

<h2>Program walk-through:</h2>

<p align="center">
Topology in use <br/>
<img src= "images/topology 1.PNG" height="80%" width="80%"/>
 <br />
 The topology we are using has two subnets a inside interface and a dmz connected to 
 an asa firewall connected to the outside network.<br/>
<br />
<br />
Install updates<br/>
<img src="images/install-files 1.PNG" height="80%" width="80%"/>
 <br />
Update ubuntu using using sudo apt-get update before installing bind9.<br />
<br />
<br />
Install bind9<br/>
<img src="images/named.conf.options 3.PNG" height="80%" width="80%" />
 <br />
  Set up the named.conf.options file with an acl so only permited clients can this
  dns server This is also where we allow queries and set up forwoarders. This file 
  will be set up simmilar to the master server. <br />
<br />
<br />
<br/>
<img src="images/name.conf.local-slave 4.PNG" height="80%" width="80%" />
 <br />
 Change the dns address to the address of the secondary server.<br />
<br />
<br />
 blank<br/>
<img src="images/check-conf 5.PNG" height="80%" width="80%" />
 <br />
 text<br />
<br />
<br />
 blank<br/>
 <img src="images/named.conf.local 6.PNG" height="80%" width="80%" />
 <br />
 <br />
<br />
<br />
 blank<br/>
 <img src="images/named.local-master 7.PNG" height="80%" width="80%" />
 <br />
 We have to tell the primary server the address of the secondary server so it knows 
 where to sent the copy of the zone file. Im also going to allow the primary server to
 notify the secondary server when changes happen.text<br />
<br />
<br />
  blank<br/>
 <img src="images/remote-client-test 8.PNG" height="80%" width="80%" />
 <br />
 Im on a client pc and changed the nameserver in the netplan file to use only the secondary
 server. I can resolve domain names from my zone so it is working.<br />
<br />
<br />
    use command () to check if packets are being encrypted <br/>
 <br />
  <img src="images/" height="80%" width="80%" />
 text<br />
<br />
<br />
  packet capture <br/>
  <img src="images/" height="80%" width="80%" />
 text<br />
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
