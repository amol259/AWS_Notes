* Understand THIS VERY WELL
###### THis only is used in IPV4, IPV6 has many ip addresses so its not needed there
Addresses the growing shortage of IPV4 shortages
IPv4 are either publically routable (allocated via ISP) or they are private
Private adresses can be used in multiple places but can't be routed over the internet so to give internet access to these private addresses we can use NAT!
Satic NAt is what you use when certain private addresses need access to the internet using a public IP where these ip's need to be consistent
Dyanmic NAT -allocated dynamically, large # of private addresses but less public addresses so you want to be efficent
PAT - What your home router does, Many private translated into 1 ip address. Many devices (laptops, computer,tablets) use pat/overloading to get 1 ip address for all these devices. (Used within AWS)
![[NAT.png]]

## Static NAT
Need to translate private addresses on left to a public one
Router in middle is default gateway for any destinations


![[Static Network Address Translation.png]]

### Dynamic NAT
Multiple devices can share the same public IP as long as theres no overlap (NOT accessing at the same time) 
Devices are not allocated a permanent IP
SO in this scenario we have 4 devices but only 2 public IP's

![[Dynamic NAT.png]]

# Port address Translation
### Understand how this works!
Used on your home network, allows a large number of private devices share the same public IP address
The destination port is what the service runs on, the public source port is randomly assigned by the client
Normally reason why 1 device can use the same ip is bc the source part is unique, so the NAT creates a NAT Table
![[PAT.png]]


### IPV4 Subnetting
### IPV4 Adressing
Rewatch and understand IP Ranges
With a few exceptions all public IPV4 addressing is allocated, you cant just use a random IP on the internet
/0 - entire internet
/8 - class
/16 - Class B
/24 - class c
/32 - single IP
![[IPV4 Addressing.png]]

IPv6 - more than a billion / human! With Ipv6 the concept of address spaces as  a commodity is  gone!

###  IP Subnetting
##### Subnetting is the process of taking a large network and breaking it down into smaller networks, each of which has a higher prefix, which indicates a smaller network

The larger the prefix value, the smaller the network
/16 tells us the network part is the 1st 2 octets
If you were allocated 1 range in your org, but we want to break it down into 4 networks.
/16 => 2 * /17
The entire network is a /0 network
![[IP Subnetting.png]]

Practice doing this by hand, it just takes a bit of practice
![[IP Subnetting 3.png]]