# SNI/ESNI

## SNI (Server Name Indication)

SNI tells a web server which TLS certificate to show at the start of a connection between the client and server. SNI is an addition to the TLS protocol that enables a 
server to host multiple TLS certificates at the same IP address.

It is an extension to the Transport Layer Security (TLS) computer networking protocol by which a client indicates which hostname it is attempting to connect to at the 
start of the handshaking process. This allows a server to present one of multiple possible certificates on the same IP address and TCP port number and hence allows
multiple secure (HTTPS) websites (or any other service over TLS) to be served by the same IP address without requiring all those sites to use the same certificate. 
It is the conceptual equivalent to HTTP/1.1 name-based virtual hosting, but for HTTPS. This also allows a proxy to forward client traffic to the right server during TLS/SSL handshake. The desired hostname is not encrypted in the original SNI extension, so an eavesdropper can see which site is being requested.

Think of SNI as being like the apartment number on a mailing address: multiple apartments are in one building, so each apartment needs a different number to 
distinguish it. Similarly, while the server is indicated by the IP address, a client device needs to include SNI in its first message to the server to indicate which 
website (which apartment) it is trying to reach.

![image](https://user-images.githubusercontent.com/7610065/158061111-4dc60314-84ec-44c9-94d7-26374a851af7.png)

## ESNI (Encrypte dServer Name Indication)

Encrypted server name indication (ESNI) is an essential feature for keeping user browsing data private. It ensures that snooping third parties cannot spy on the TLS 
handshake process to determine which websites users are visiting. ESNI, as the name implies, accomplishes this by encrypting the server name indication (SNI) part of the
TLS handshake.

ESNI keeps SNI secret by encrypting the SNI part of the client hello message (and only this part). Encryption only works if both sides of a communication — in this case,
the client and the server — have the key for encrypting and decrypting the information, just as two people can use the same locker only if both have a key to the locker.
Because the client hello message is sent before the client and server have negotiated TLS encryption keys, the ESNI encryption key has to be communicated some other way.

The solution: public key cryptography. The web server adds a public key to its DNS record, so that when the client looks up where to find the right server, it finds 
the server's public key as well. This is somewhat like leaving a house key in a lockbox outside one's home so that a visitor can safely enter the home. 
The client can then use the public key to encrypt its SNI record in such a way that only that specific server can decrypt it.

Imagine that Alice wants to visit Bob's website, www.bobisawesome.example.com. Like every responsible website owner should, Bob uses TLS for his website so that all 
traffic to and from his website is encrypted. Bob has also implemented ESNI to further protect site visitors like Alice.

When Alice types https://www.bobisawesome.example.com into her laptop's browser, her laptop goes through the following process for loading the website:

- Her laptop sends a query to a DNS server to find out the website's IP address.
- The DNS response tells Alice's laptop which IP address to use in order to find Bob's website, and the DNS response also includes Bob's ESNI public key.
- Alice's laptop sends a client hello message to the indicated IP address, encrypting the SNI part of the message by using Bob's public key.
- Bob's web server shows Bob's TLS certificate.
- The TLS handshake proceeds, and Alice's laptop loads www.bobisawesome.example.com. Any attackers who may be monitoring the network cannot see which website Alice is visiting.*

*This last statement is only true if the DNS part of the process used DNSSEC and either DNS over HTTPS or DNS over TLS otherwise attacker can sniff DNS entries. to prevent sniff both ESNI and DNSSEC has to be in place

