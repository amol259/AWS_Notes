Any change no matter how minor changes the hash value
![[hashing.png]]

Examples of hashing used
The password will still exist on the server, so it is vulnerable. SO what if we use hashes?
This way the server uses the hash and the server checks if the hash you send matches the hash on the server, this way it can check i you have the right password without every storing the password!
![[HashExample.png]]

### Bad things about Hashing
Collision: ![[collisions.png]]

2 diferent pieces of data generate the same hash value - happens on older hashing algorithims
![[Hashing Summary.png]]