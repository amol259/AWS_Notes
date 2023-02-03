Builds of: [[Layer 1]]

Focused on ethernet for now
MAC Address - Not software assigned, attached to physical hardware so it should be unique
[Layer 1] handles the physical transmitting of raw data onto the physical medium. Layer 2 deals with Frames, among other things.

### # Components of a Frame:
Preamble - Identifies its a start of a frame
Destination Mac Address: A frame can be sent to a specific device on a network by putting its mac address on its destination field
Source MAC Address - Tells the originiating MAC device
ET - Layer 3 uses layer 2 frames for device to device communication on a local network, so when you receive a frame on the other side of the communication you need to know which protocol originally put data in the frame (could be IP)

#### Mac Header
The 4 above is the mac header which controls the frame destination, indicates the source, and specifies the function

##### Encapsulation - You have something layer 3 generates, often a ip packet, which is put inside (encapsulated) a ethernet frame. The frame delivers that data to a layer 2 destination, the ET field isused to determine which layer 3 protocol received the frame at the destination.
Frame Check Sequence - Identifies any errors in the frame, checks if corruption has occured or not

![[Layer 2 - Data Link - Frame.png]]

Layer 1 doesnt understand the frame as anything more than a block of data, it will 
Layer 2 uses layer 1 to transmit and receive the raw data, but it adds ontop of this Mac addresses which allow for machine to machine communication, and it adds media access control.
Layer 2 is adding the media acces control which checks for the carrier and only sends the frame down to layer 1 for transmission. 
![[Layer 2 - Data Link CSMA.png]]

What if both machines check for carriers at same time and tells Layer 1 to transmit at the same time? That is a collision, if a collision is detected than a Jam signal is sent and a back off occurs.

![[L2 Hub.png]]
Swtich - works sameway physically as a hub but understands Layer 2, 

![[L2 Switch.png]]

# Layer 2 Recap/Benefits
1. Identifiable Devices
2. Media Access Control (Sharing access to physical media)
3. Collision Detection
4. Unicast 1:1
5. Broadcast 1:All
6. Switches - hubs with superpowers lets us scale 