### Come back and Review

Very useful in hybrid networking
Each port is a different collision domain 
Each color is a different set of user groups
[[Layer 2]]
![[physicalSegments.png]]

This is how things would look in the real world if we only had access to physical networking, which is fine if the different colors don't need to communicate with eachother
![[Physical Segment.png]]

## Frame Tagging
We need to create a new type of frame for VLAN
A broadcast frame (all F's ) only can communicate to all devices in its own network
![[FrameTagging.png]]
802.1AD - nested VLANS

### In this visual you have 2 different networks, both are isolated and can't communicate without a layer 3 Router.
Used in AWS DirectConnect
![[VlanDetailed.png]]

### Summary
Traffic Isolation - If you don't deploy/configure a router the 2 networks frames cannot leave the vlan boundary so they're virtual networks
We want to do this when we need different networks for different customers!
![[VLANSUMMARY.png]]