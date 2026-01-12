## Static routing is used because it:
-<b>Gives full control over routing paths

-<b>Consumes no bandwidth (no routing updates sent)

-<b>Is more secure (no route advertisements)

-<b>Is predictable and stable

-<b>Works well for small or simple networks

## Common real-world use cases

-<b>Small office networks

-<b>Stub networks (networks with only one exit path)

-<b>Backup routes

-<b>Default routes to the internet


## CONFIGURATION PROCEDURE:
## ON ROUTER 1
R1>En

R1#CONFIG T


R1(CONFIG)#INTERFACE GIGABITETHERNET0/0

R1(CONFIG-IF)#IP ADDRESS  192.168.10.1 255.255.255.192

R1(CONFIG-IF)#NO SHUTDOWN

R1(CONFIG-IF)#EXIT

R1(CONFIG)#INTERFACE GIGABITETHERNET0/1

R1(CONFIG-IF)#IP ADDRESS 192.168.30.1 255.255.255.240

R1(CONFIG-IF)#NO SHUTDOWN

R1(CONFIG-IF)#EXIT

R1(CONFIG)#INTERFACE SERIALO/2/0

R1(CONFIG-IF)#IP ADDRESS 10.0.0.1 255.255.255.252

R1(CONFIG-IF)NO SHUTDOWN

R1(CONFIG)#IP ROUTE ?

R1(CONFIG)#IP ROUTE 192.168.20.0 255.255.255.224 ?

 R1(CONFIG)#IP ROUTE 192.168.20.0 255.255.255.224 10.0.0.2

 R1(CONFIG)#IP ROUTE 192.168.40.0 255.255.255.128 ?

 R1(CONFIG)#IP ROUTE 192.168.40.0 255.255.255.128 10.0.0.2

 R1(CONFIG)#




## ON ROUTER 2
R2>EN

R2#CONFIG T

R2(CONFIG)#INTFACE GIGABITETHERNET0/0

R2(CONFIG-IF)#IP ADDRESS 192.168.20.1 255.255.255.224

R2(CONFIG-IF)#NO  SHUTDOWN

R2(CONFIG-IF)#EXIT

R2(CONFIG)#INTERFACE GIGABITETHERNET0/1

R2(CONFIG-IF)#IP ADDRESS 192.168.40.1 255.255.255.128

R2(CONFIG-IF)#NO SHUTDOWN

R2(CONFIG)#INTERFACE SERIAL0/3/0

R2(CONFIG-IF)#IP ADDRESS 10.0.0.2 255.255.255.252

R2(CONFIG-IF)#NO SHUTDOWN

R2(CONFIG)#IP ROUTE ?

R2R2(CONFIG)#IP ROUTE 192.168.10.1 255.255.255.192 ?

R2(CONFIG)#1P ROUTE 192.168.10.1 255.255.255.192  10.0.0.1

R2R2(CONFIG)#IP ROUTE ?

R2(CONFIG)#192.168.30.1 255.255.255.240 ?


R2(CONFIG)#192.168.30.1 255.255.255.240 10.0.0.1

R2(CONFIG)#

<h2>Project walk-through:</h2>

<p align="center">
Network Diagram: <br/>
<img src="https://imgur.com/QK3gSUJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
IP Structure for the Network:  <br/>
<img src="https://imgur.com/iCNLwhL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Deploying the VMs:  <br/>
<img src="https://imgur.com/LJtp1Jy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Setting up the CEO PC IP address:  <br/>
<img src="https://imgur.com/5wUQ9cK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Connectivity Test on The Network using ping utility:  <br/>
<img src="https://imgur.com/tF9LuAs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Performing Scanning Using NMAP Against DNS-Server:  <br/>
<img src="https://imgur.com/d9qn2C6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Running an Active Scan Using NMAP RESULTS FOR WEB SERVER:  <br/>
<img src="https://imgur.com/oRkSG5K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Running a Connectivity Test from a Untrusted Network to Trusted Network:  <br/>
<img src="https://imgur.com/XNZAvuI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Capturing Packets Using WireShark:  <br/>
<img src="https://imgur.com/WppeLFw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
</p>

<h2>Conclusion</h2>
This project successfully demonstrates the design, configuration, and validation of a static routing–based network in a controlled environment. By manually assigning IP addresses to router interfaces and defining explicit static routes, full control over traffic flow between multiple subnets was achieved. The configuration proved to be stable, predictable, and secure, as no routing updates were exchanged and all routing decisions were explicitly defined by the network administrator.

Connectivity tests using the ping utility confirmed proper end-to-end communication between trusted and untrusted networks, validating the correctness of the IP addressing scheme and static routes. Security and visibility were further enhanced through Nmap scanning, which provided insight into exposed services on the DNS and web servers, and Wireshark packet captures, which allowed for real-time traffic analysis and protocol inspection.

Overall, this implementation highlights why static routing is well-suited for small networks, stub networks, and backup paths, where simplicity, low overhead, and administrative control are critical. The project also reinforces key networking and cybersecurity concepts such as IP planning, traffic analysis, and network testing, making it a solid practical foundation for more advanced routing and security implementations in larger or dynamic environments.



