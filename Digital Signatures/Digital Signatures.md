
NEED TO BE FAMILIAR WITH THIS For SSL and DNS SEC!
### UNDERSTAND THIS E2E
[[SSL and TLS]]
#### Cryptography refresher (Signing Archeticture)

![[Crypt Refresher.png]]
#### Digital Signatures
This creates a chain of trust!
![[Digital Signatures.png]]

Wider distribuition of public key, easier it is to spot if its been altered!
Signing the data: A hash of the data doesn't prove that bob created the document so he uses his private key to sign the hash, which signals ownership since no one but bob has the private key

Someone else getting the data: Download signed data and to get Bobs original hash you take the signature and bobs public key to get the hash of the data. Then you hash it with the same hash algo bob used.![[digital signature visual flow.png]]

Hash + Priovate key to sign 
Decrypt:
Digitally signed data as input to a hash function which gives us a hash. Then you could use the public key to get the og hash and if those 2 match, then you know that the doc hasn't been altered & you know which private key was used to sign it
