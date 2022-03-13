# DNS

DNS is the phonebook of the Internet; DNS resolvers translate human-readable domain names into machine-readable IP addresses. By default, DNS queries and 
responses are sent in plaintext (via UDP), which means they can be read by networks, ISPs, or anybody able to monitor transmissions. Even if a website uses HTTPS, 
the DNS query required to navigate to that website is exposed.

This lack of privacy has a huge impact on security and, in some cases, human rights; if DNS queries are not private, then it becomes easier for governments to censor 
the Internet and for attackers to stalk users' online behavior.

![image](https://user-images.githubusercontent.com/7610065/158064352-026dcf75-b0f8-4edf-8234-cabd4ab81a5d.png)

DNS over TLS and DNS over HTTPS are two standards developed for encrypting plaintext DNS traffic in order to prevent malicious parties, advertisers, ISPs, and 
others from being able to interpret the data. Continuing the analogy, these standards aim to put an envelope around all postcards going through the mail, so that 
anyone can send a postcard without worrying that someone is snooping on what they are up to.

## DOT

DNS over TLS, or DoT, is a standard for encrypting DNS queries to keep them secure and private. DoT uses the same security protocol, TLS, that HTTPS 
websites use to encrypt and authenticate communications. (TLS is also known as "SSL.") DoT adds TLS encryption on top of the user datagram protocol (UDP), 
which is used for DNS queries. Additionally, it ensures that DNS requests and responses are not tampered with or forged via on-path attacks.

## DOH

DNS over HTTPS, or DoH, is an alternative to DoT. With DoH, DNS queries and responses are encrypted, but they are sent via the HTTP or HTTP/2 protocols instead of 
directly over UDP. Like DoT, DoH ensures that attackers can't forge or alter DNS traffic. DoH traffic looks like other HTTPS traffic – e.g. normal user-driven 
interactions with websites and web apps – from a network administrator's perspective.

## Difference

Each standard was developed separately and has its own RFC* documentation, but the most important difference between DoT and DoH is what port they use. DoT only uses 
port 853, while DoH uses port 443, which is the port that all other HTTPS traffic uses as well.

Because DoT has a dedicated port, anyone with network visibility can see DoT traffic coming and going, even though the requests and responses themselves are encrypted. 
In contrast, with DoH, DNS queries and responses are camouflaged within other HTTPS traffic, since it all comes and goes from the same port.

## Which is better, DoT or DoH?
This is up for debate. From a network security standpoint, DoT is arguably better. It gives network administrators the ability to monitor and block DNS queries, 
which is important for identifying and stopping malicious traffic. DoH queries, meanwhile, are hidden in regular HTTPS traffic, meaning they cannot easily be blocked
without blocking all other HTTPS traffic as well.

However, from a privacy perspective, DoH is arguably preferable. With DoH, DNS queries are hidden within the larger flow of HTTPS traffic. This gives network 
administrators less visibility but provides users with more privacy.
