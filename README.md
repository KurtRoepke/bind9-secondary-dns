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
Create named.conf.options <br/>
<img src= "images/copy options file 1.PNG" height="80%" width="80%"/>
 <P>Create a named.conf.options file that matches the file on the primary server.
 just change the listen on ip address to match the secondary server.</P> <br/>
<br />
<br />
Create named.conf.local<br/>
<img src="images/create zones 2.PNG" height="80%" width="80%"/>
<p>Create zones in the named.conf.local file. create a link to the master server
using the master servers ip. Next allow for the secondary server to notify the primary
server it could come in handy for troubleshooting.</p>
<br />
<br />
Transfer on master<br/>
<img src="images/allow transfer on master 3.PNG"  height="80%" width="80%"/>
<p>Allow the transfer on the master server and adding the ip address to the secondary
server. Then allow for the master to notify the the secondary of changes again 
could come in handy for troubleshooting ask me how i know.</p>
<br />
<br />
Create ikev2 policy<br/>
<img src="images/permissions 4.PNG" height="80%" width="80%" />
<br />
<br />
Create ikev2 profile <br/>
<img src="images/netplan 5.PNG" height="80%" width="80%" />
<br />
<br />
Create transform set<br/>
<img src="images/" height="80%" width="80%" />
<br />
<br />
 Create ipsec profile<br/>
 <img src="images/" height="80%" width="80%" />
<br />
<br />
 Map ipsec profile to gre tunnel<br/>
 <img src="images/" height="80%" width="80%" />
<br />
<br />
  Ping pc on other network <br/>
 <img src="images/" height="80%" width="80%" />
<br />
<br />
    use command () to check if packets are being encrypted <br/>
  <img src="images/" height="80%" width="80%" />
<br />
<br />
  packet capture <br/>
  <img src="images/" height="80%" width="80%" />
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
