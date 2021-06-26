# Internet

- [Fullstack](../README.md)

## What's Internet?

A system of globally publicly interconnected devices. When it's a private connection it's called Intranet.

LAN - local area network

WAN - wide area network

## How does it work?

Domain hits a nameserver. Nameserver looks up a DNS record and returns an IP that gets passed through routers, nodes and switches and eventually hits the server. Server routes further.

### Internet Protocol

A protocol that defines format of data, how to read it, write it and send it back.

### IP Address

Label assigned to the device connected to the internet.

IPv4 - 4.3 billion addresses
IPv6 - 3.4 \* 10^38

### TCP

Transmission Control Protocol - negotiates connection for each file sent.

It's lossless, guarantess that the information is gonna reach its target.

Server sends SYN packet and client has to answer with ACK.

TCP has error correcting. Server receives bunch of packets, makes a checksum and requests any packets that were missing.

### UDP

User Datagram Protocol - negotiates connection and leaving the communication open while it talks with the same server.

It's fast. Used in streaming audio/video.

### DNS

Domain Name System - "Intelligent Internet Phone Book", when you go to a domain you ask DNS "what's the closest server this resolves to". Maps domain names to IP addresses.

```md
subdomain.domain.tld
```

- TLD - owned by specific entities, companies or countries
- domain - registered name in DNS
- subdomain - still routes to main domain, but probably different part of the site

Records are kept in name servers.

#### DNS Record Types

- **A record** - name to IP
- **CNAME** - name to name

### ICMP

Protocol for health checks.

### Packet

Little bit of information you can transmit. "Envelope" with an address, addressee and the data.

It's mostly metadata in form of headers.

## Net Neutrality

Should ISP be just "dumb pipes" sending traffic or should they be allowed to prioritize.

## Black holing

Not responding to requests.

## Tools

### Ping

Poking the server - "you there?"

### Traceroute

Shows map of servers on a connection to a particular domain.
