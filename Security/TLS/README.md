# TLS

Transport Layer Security, or TLS for short, is an encryption protocol that keeps communications private and secure on the Internet. TLS is used mostly to encrypt the communication between applications and web servers, like when web browsers load a website. All websites that use TLS must have a TLS certificate. TLS is sometimes called SSL, although SSL is an outdated name for the protocol.

All TLS connections start with something called a "handshake." Just as a handshake is used in real life when two people meet and exchange introductions, the TLS handshake is a series of introductory communications between a client device (like a user's smartphone) and a web application or website. During a TLS handshake, the two communicating devices agree on what encryption keys to use, among other steps. Despite the number of steps involved, a TLS handshake takes only a few milliseconds.

## What happens during a TLS handshake

- Specify which version of TLS (TLS 1.0, 1.2, 1.3, etc.) they will use
- Decide on which cipher suites they will use
- Authenticate the identity of the server via the server’s public key and the SSL certificate authority’s digital signature
- Generate session keys in order to use symmetric encryption after the handshake is complete

## SSL certificate
An SSL certificate is a file installed on a website's origin server. It's simply a data file containing the public key and the identity of the website owner, along with other information. Without an SSL certificate, a website's traffic can't be encrypted with TLS.

Technically, any website owner can create their own SSL certificate, and such certificates are called self-signed certificates. However, browsers do not consider self-signed certificates to be as trustworthy as SSL certificates issued by a certificate authority.

## How does a website get an SSL certificate?
Website owners need to obtain an SSL certificate from a certificate authority, and then install it on their web server (often a web host can handle this process). A certificate authority is an outside party who can confirm that the website owner is who they say they are. They keep a copy of the certificates they issue.
