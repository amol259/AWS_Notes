Requires 1 or more [layer2] to be active
Layer 3 is used to actually transport data over the internet
Issue: Various layer 2 protocols are used, how to join?
pink = cable connections (point to point links)
blue = sateelite connection
Layer 3 is a common protocol which can span multiple [layer2] networks
Routers - move packets of data across layer 3 networks
IP - Layer 3 protocol used on the internet

![[L3 Network.png]]


###### Packets vs frames
Share: Data to be moved, source/destination address
Difference: For Frames, source and destination addresses are generally local
With an IP Packet, the destination/source could be on opposite sides of the planet

IP Packets remain the same during thier journey, however as they move across the layer 2 network they are placed inside frames (encapsulation) for local network on that layer2. As it moves across differnet networks, it'll be different frames but but the same packet


##### Ip Addressing
IP addressing is what identifies a device which uses layer 3 IP networking
Always read IP left to Right
IP addresses need to be unique, both locally and globally

![[IP Addressing.png]]

How to tell if 2 ip's are on the same network?
Use a submnet mask and if the network part matches, its on the same network else its remote

##### Subnet Mask

Default Gateway - IP address on local network which packets are forwareded to if the destination ip is remote
Allows an Ip device to know if an ip address its communicating with is on the same network or not , which influences if it can communicate directly or use the default gateway

Using a subnet mask:
1. Convert subnet and ip to binary - the decimal notation isnt useful 
2. Once in binary the 1's represent the network, and the 0's represent the host
3. Line up the ip and subnet, all the 1's in the subnet represent the network and the 0's represent the host

![[subnetMasks.png]]![[Subnet Mask 2.png]]

##### Route Tables & routes
How does the isp know where to forward your data to? It uses routes and route table
Every packet that arrives at the router, the router checks the destination ip address and then the router will look for any routes in the route table (if multiple match it prefers the more specific route). 
Route tables can be statically propogate or use BGP 

### IMPORTANT: When our ISP router is forwarding the packet to the AWS router, it does it via [layer 2] and encapsulates the packet in a frame

![[Routes.png]]

### Address Resolution Protocol
Once the packet is wrapped in a frame and needs to be sent to the aws router, how does it find the mac address (destination)?
ARP gives you the mac address for a given IP
Even if 2 devices are communicating via layer 3, they use layer 2 for LOCAL networks. You can have many L2 frames along the way for remote networks.

![[ARP.png]]


#### IP Routing - Brings all concepts together
Routers are l3 devices which mean they understand layer 1,2,3. They move packets between networks!
Local Communication (D1 & D2)
Remote Communcation (D2 & D3)

![[IP Routing.png]]

### Layer 3 Benefits

![[Layer 3 Recap.png]]