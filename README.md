# Backend-Engineering

when client connect to server it first does 3 way TCP handshake followed by a TLS handshake and exhange key (diffie hellman) than that encrypts client communication

<img src="https://user-images.githubusercontent.com/7610065/158075395-4c413f96-3a34-43fb-bb38-8d2d7c29722d.png" width="500" height="250">

Is there a Limit to Number of Connections a Backend can handle?

https://www.youtube.com/watch?v=o-EkdZW4zbA

https://serverfault.com/questions/723121/how-does-nginx-websocket-proxy-work

## Multitenancy

Software multitenancy is a software architecture in which a single instance of software runs on a server and serves multiple tenants. Systems designed in such manner are "shared"

<img src="https://user-images.githubusercontent.com/7610065/159543956-c24f7968-5e48-4f89-b99f-b613281335f0.png" width="500" height="250">

# Blocking and Non Blocking

Blocking socket, execution will wait (ie. "block") until the full socket operation has taken place. So, you can process any results/responses in your code immediately after. These are also called synchronous sockets.

A blocking web-server is similar to a phone call. you need to wait on-line to get a response and continue; where as a non-blocking web-server is like a sms service. you sms your request,do your things and react when you receive an sms back!

Non-Blocking socket operation will allow execution to resume immediately and you can handle the server's response with a callback or event. These are called asynchronous sockets.

Non-blocking generally means event driven, multiplexing all activity via an event driven system in a single thread, as opposed to using multiple threads.

## Communication Protocols
 - [TCP](https://github.com/Jayash/Backend-Engineering/tree/main/Communication%20Protocols/TCP)
 - [UDP](https://github.com/Jayash/Backend-Engineering/tree/main/Communication%20Protocols/UDP)
 - [Web Sockets](https://github.com/Jayash/Backend-Engineering/tree/main/Communication%20Protocols/Web%20Sockets)
 - [HTTP](https://github.com/Jayash/Backend-Engineering/tree/main/Communication%20Protocols/HTTP)
 - [IP](https://github.com/Jayash/Backend-Engineering/blob/main/Communication%20Protocols/IP)
 - [ICMP](https://github.com/Jayash/Backend-Engineering/tree/main/Communication%20Protocols/ICMP)
 
## Web Servers
## Database Engineering
## Proxies
## Caching
## Messaging System
## Web Frameworks Runtime
## Message Formats
- XML
- JSON
## Security
- [TLS](https://github.com/Jayash/Backend-Engineering/tree/main/Security/TLS)
- [Symmetric and Asymmetric Keys](https://github.com/Jayash/Backend-Engineering/tree/main/Security/Symmetric%20vs.%20Asymmetric%20Encryption)
- [Secure DNS](https://github.com/Jayash/Backend-Engineering/tree/main/Security/Secure%20DNS)
- [SNI/ESNI](https://github.com/Jayash/Backend-Engineering/blob/main/Security/SNI-ESNI/README.md)

## Proxy vs Reverse Proxy

<img src="https://user-images.githubusercontent.com/7610065/173232079-8d1a02fe-19ee-4652-8f33-0298fd715ffb.png" width="500" height="250">

<img src="https://user-images.githubusercontent.com/7610065/173232194-ffd867e3-81cd-4fa7-b4cb-5d02badc66d1.png" width="500" height="250">

<img src="https://user-images.githubusercontent.com/7610065/173232269-7d83b85f-13c9-4dc8-bbc3-f42f13cb531f.png" width="500" height="250">

<img src="https://user-images.githubusercontent.com/7610065/173232301-a30bbf20-b166-4ce3-8170-0df2df7b71dc.png" width="500" height="250">

