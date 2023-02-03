With IP Theres no gurantee of packet delivery
Every packet in [Layer3] is different! What happens to 1 packet might not happen in another

![[Layer 3 Problems.png]]


#### TCP vs UDP
TCP - Slower but reliable
UCP  - Fast but unreliable
Both run on top of IP and use IP as transit!
![[TCPvsUDP.png]]

### TCP Segments
Add additional capabilities to IP packets
TCP segments add source and destination ports, which gives the ability to have multiple streams of conversations between 2 devices
Ports allow multiple streams of communcation, each converstaion is a unique combo of source ip/port, destination ip/port
Sequence # - Way of uniqiuely identifying a particular segment 
Acknowldgement - Every segment needs to be acknowledged, 1 side can indicate its received upto and including a certain sequence number. if device 1 transmits 1,2,3,4 the other device goes receieved 1, 2,3,4
Checksum - used for error checking, can arrange for retransmiision of data
urgent pointer - Both sides can have seperate processing so control traffic can always take prioirty, used for latency sensitive or data transfer.
![[TCP Segments.png]]

### TCP
Layer 4 takes data provided to it, chops it up into segments, encapsulate those into IP packets but thye're linked to a connection so they are in ORDER!
Bidirectional means server can send data back to the client, to do this it just flips the destination port to source port and vice versa
![[TCP.png]]

Need 2 set of ports on a network ACL in AWS:
1 set for initating part: Laptop to server
1 set for response part: Server to Laptop
Ephermal or high port - port range client picks as source port

### TCP Connection - 3 way Handshake
With TCP everything is based on connections, so before it transfers data it establishes a connection via 3 way handshake
1. Client send SYN to server - Hey server open a connection
2. Server send SYN-ACK - SUP client, sure thing. Open your side for me
3. Client Replies ACK - Say no more fam

![[TCP 3 way handshake.png]]


![[TCP S1.png]]

![[TCP S2.png]]![[TCP S3.png]]


### Sessions & State
Well known port - tcp 443
If you wanted to add security to a firewall, what type of rules would you want to have to allow inbound communications? 
Stateless firewall - Doesn't understand state of connection
Network ACl = stateless firewall
* Need to understand how security roles are created for stateful/stateless firewall
![[State vs Stateless firewall.png]]

Session - ongoing communcication 