[[DNS]] 
[[hashing.png]]
[[Digital Signatures]]
### Come back and Review
Analogy is to think of dns as http and dnssec is https, it secures dns and adds to DNS!
![[DNSSEC Benefits.png]]

DNSSEC doesn't correct anything, it just validates if somethings from source and if its been altered!
![[DNSSEC Visual.png]]

### Example of DNS Attack
![[DNS Disrupted.png]]

#### DNSSEC in a Zone
RRSIG - digital signature of the record it points to
covers [[Digital Signatures]] within DNSSEC
Resource record set = RRSET any records of the same name and same type. Makes it easier to deal with records in groups rather than individually

![[RRSET.png]]

DNS allows us to validate data integrity of valid sets, it doesn't work for individual records, rather it works on set of records (RRSETS)
2 features to prevent malicious activity:
1. RRSIG which stores digital signature using private/public keys of a  RRSET. 
2. ZSK - The private key part is not stored in the zone, only the user has it hidden.
Only the private part of the zsk can generate the asset so you can tell if it's altered! The only risk is the private key being found.
![[RRSIG.png]]
If theres a valid RRSIG for a RRSET you can trust the record
RRSIG MX - SIgned RRSIG
MX + ZSK Public + RRSIG MX = valid RRSET ASSUMING you trust DNSKEY specifically the zsk. YOu have to trust the zone admin has the private key and that its the correct zsk! 
KSK - Used for signing Keys, Creating the DNSKEY RRSIG Record
ZSK - Used for signing everything in a zone EXECEPT for DNSKEY
![[DNSKEY 1.png]]

Need a way of ensuring the zsk is trusted? 
Thus this zone is linked to the parent zone by cryptogrpahic trust. Best practice is to cycle keys often so you don't want constant parent zone changes. 

![[DNSSEC - KSK.png]]

What have we gained with DNSSEC:
1. Data Integrity protection - can trust all the information within a zone

Things to know
1. How DNSSEC validates things in 1 zone
2. How it uses RRSIGS to validate RRSETS
3. How it uses DNS key records to do that validation using the zone signing key
4. How a key signing key is used to create an RRSIG at the DNSKEY which allows the validation of that DNSKEY record
5. How the parent domain trusts the public key signing key at the child domain or zone
6. Why 2 different keys are needed

### DNSSEC CHAIN OF TRUST
COME BACK AND REVIEW
DS - Record
![[DNSSEC Validation Flow.png]]

### DNSSEC Signing Ceremony
Controlling the trust anchor of the internet - everything you use on the internet does this
Trust within a dns zone is provided via the parent zone of that zone, the parnet zone has a dns record which is a hash of the public ksk. 

Trust Anchor:
WIth them you define whats valid within dns zones, so everything relies on this
The root zone is trusted via this signing process
![[DNSSEC Trust Anchor.png]]

![[DNSSEC SIgning Ceremony.png]]

