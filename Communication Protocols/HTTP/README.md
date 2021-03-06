# HTTP

HTTP protocal is stateless, most of the time it uses TCP which is statefull and can also use UDP

OSI Layer 7 Protocol

![image](https://user-images.githubusercontent.com/7610065/158011569-a94f31ca-f3b6-4158-abf0-e7a43ec83fe1.png)

![image](https://user-images.githubusercontent.com/7610065/158011597-29a46d25-1de9-497d-a3c3-aadce6d9a6fa.png)

## open connection
- To open a connection we have to do 3-way handshake
![image](https://user-images.githubusercontent.com/7610065/158012560-34874d26-0b4c-4de2-a935-6a831a15e177.png)

## close connection
- The connection termination phase uses a four-way handshake, with each side of the connection terminating independently. When an endpoint wishes to stop its half of the connection, it transmits a FIN packet, which the other end acknowledges with an ACK.
![image](https://user-images.githubusercontent.com/7610065/158012572-5eb72224-7272-4fcc-848b-0fe23571b68b.png)

## HTTP 1.0 (1996-1997)

open-close connection for each request

![image](https://user-images.githubusercontent.com/7610065/158011981-8a605e80-7da8-41c1-acad-3d9485335245.png)
![image](https://user-images.githubusercontent.com/7610065/158011956-fb851532-df1b-496a-86d9-a32db4491c15.png)

## HTTP 1.1 (1997-2015)

Keep alive header also send with the request and connection is only closed if server serves all the client requests, this also brings concepts of e-tags and caching

![image](https://user-images.githubusercontent.com/7610065/158012097-18d6953c-196b-4277-8833-3afb7a89f4c3.png)
![image](https://user-images.githubusercontent.com/7610065/158012082-e5c46d90-db2c-49d1-ba38-200c172857a1.png)

Chunked transfer encoding: The data stream is divided into a series of non-overlapping "chunks". The chunks are sent out and received independently of one another. No knowledge of the data stream outside the currently-being-processed chunk is necessary for both the sender and the receiver at any given time. Each chunk is preceded by its size in bytes. The transmission ends when a zero-length chunk is received. The chunked keyword in the Transfer-Encoding header is used to indicate chunked transfer. Chunked transfer encoding is not supported in HTTP/2, which provides its own mechanisms for data streaming. 

This is usually required when an HTTP client is reading a response message from a server it needs to know when it has reached the end of the message. This is particularly important with persistent (keep alive) connections, because a connection can only be re-used by another HTTP transaction after the response message has been fully received.

HTTP Pipeline 

![image](https://user-images.githubusercontent.com/7610065/158013379-ef4bf1ea-c23a-4039-a603-4230e5bcc2b8.png)

Note: Browsers ultimately did not enable pipelining by default, and by 2017 most browsers supported HTTP/2 by default which used multiplexing instead because of Head-of-line blocking(HOL) problem i.e. Even if the server does properly support pipelining, performance issues can arise because all subsequent requests have to wait for the first one to be complete.

Because of HOL HTTP 1.1 is slow so browser has a around and it opens 6 HTTP connection and request on 6 parallelly (reuse the existing connection for all the request of 7 requests comes last request has to wait for at least one to complete) but it will cause same thing if we have to call server more than 6 times parallelly.

![image](https://user-images.githubusercontent.com/7610065/158016816-a9f5b5c0-8952-435d-865e-63b00bb66cf7.png)

## HTTP 2.0 (2015-Now)

![image](https://user-images.githubusercontent.com/7610065/158012237-288a081c-5b01-489e-ae94-d303339b34e3.png)

- Multiplex: Permits multiple requests and responses to be sent at the same time.
- Compression: Compresses headers that have been requested previously to make things more efficient.
- Server push: The server can send additional information needed for a request before it is requested
- Increased security: HTTP/2 is supported through encrypted connections

![image](https://user-images.githubusercontent.com/7610065/158016943-e990f28a-7184-4afd-bd4d-3efd91cd77eb.png)

## HTTP 3.0

Still experimental

![image](https://user-images.githubusercontent.com/7610065/158012424-b0ccf7d6-de1a-449f-b732-2d8b4b328582.png)

