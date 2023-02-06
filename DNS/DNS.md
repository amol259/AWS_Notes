At its core its like a big contact database, it links contacts/DNS names (urls) to IP addresses. ![[DNS 101.png]]

### Why do we need lots of dns servers?
1. Risk - hackers can attack it
2. Scaling
3. Data Volume

![[DNS Server Question.png]]


We want to ensure uk websites are managed by people in the uk, .gov in us be managed by people in the US.

### Key Terms - know these
Authorative - single source of truth for that zone
![[DNS Terms 101.png]]

Root zone is just a database, it doesn't store much data but has info on Top Level Domain. Its job is really just to point to TLD registries. Other tld could be .au, .iu,...

Name servers for netflix.com are authoritative for netflix.com
![[Hierarchical design of DNS.png]]
Each layer of DNS only stores a small part of the information used in DNS

### How DNS Works
Function of DNS is to find you the right zone
![[What do we want from DNS?.png]]

How most internet apps work so its critical to understand fully!
Because no 1 single namespace has all the answers, every query gives you the next step 
![[Walking the Tree.png]]![[Tree Tech.png]]

### Registering A Domain
Route 53 - Domain Registrar Area
R53 Hosted Zones - DNS Hosting Provider Area
Key:
domain Registrar - Register domain w/ the registry
Hosting provider - hosts the zone for the domain name on the servers
![[Domain registrar.png]]

### How DNSSEC Works within a zone
[[Digital Signatures]]
