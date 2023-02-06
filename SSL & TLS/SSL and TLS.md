### Secure Socket Layer and Transport Laye 
#### COme back and Review

[[Asymmetric Encryption.png]]
[[Symmetric Encryption.png]]

![[SSL and TLS Overview.png]]

Cipher Suite:
Uses [[Asymmetric Encryption.png]] which is very computationally heavy and we want ot move away from it as fast as possible
We can't just trust any certificate, else hackers could just make a fake cert, this is why authentication is needed. need to prove serverId is valid using the CA
Cipher suite - set of encryption algorithims
CA - Public certificate authority 
REWATCH TO UNDERSTAND

![[TLS.png]]

High Level what happens anytime you communicate with a https server:
1. Verify identity of server
2. Negotiate encryption method 
3. Exchange assymetric for symmetric encryption keys
4. Initate secure communication channel

 ### Other visulaizations
 
![[Screen Shot 2023-02-05 at 8.58.16 AM.png]]