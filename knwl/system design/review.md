# Review - Dec. 06, 2025

## Set 1: Foundation-Building

1.  What does the acronym DNS stand for, and what is its fundamental purpose as described in the notes?

Answer:

```
DNS stands for Domain Name System. It is the phonebook of the internet that allows a domain name such as google.com to map into a serer address that is in the form of IPv4, improving the accessibility as users don't need to memorize long numbers.
```

2.  List the four distinct types of DNS servers that collectively resolve domain names.

Answer:

```
The four types of server involve in DNS are:
1. Recursive resolver
2. Root Nameserver
3. TLD server
4. Authorative Server
```

3.  Why is a DNS recursive resolver considered the "middleman" in the name to address translation process?

Answer:

```
The query client is receive by recursive resolve wherein it queries the other servers until it gets into the authorative server and get the address in which the resolver will return to the client. Technically, the resolver is the one that communicates to the client and the other servers acting as the **middleman**.
```

4.  According to the notes, what specific information does a Root nameserver provide to a recursive resolver?

Answer:

```
The root nameserver respond with the specific TLD servers.
```

5.  What happens if a DNS recursive resolver already has cached data for a queried domain name?

Answer:

```
It will return the cache data.
```

6.  How do TLD servers differentiate between types of domain names they manage?

Answer:

```
It depends on their Top-level domain such as: .com, .net, .org, etc.
```

7.  What is the primary function of an Authoritative nameserver in the DNS resolution process?

Answer:

```
It contains the DNS records which is what the client needs.
```

8.  Which entities are mentioned as potential hosts for DNS recursive resolvers?

Answer:

```
Your ISP, routers, or public DNS such as: Google, Cloudflare, etc.
```

## Set 2: High-Difficulty Synthesis

1.  Describe the complete flow of a DNS query from a client to an Authoritative nameserver, detailing the interaction between each type of server involved, assuming no cached data exists.

Answer:

```
The client query a domain in their browsers. The query will go through the the recursive resolver to manage your query. First, it will request to the root nameserver to get the TLD server. Once the resolver had the address to the TLD server, it will request to it then to get the Authorative server which will return the DNS records that the client needs.
```

2.  Explain how the distributed nature of Root nameservers (13 clusters, ~600 servers) contributes to the overall resilience and performance of the DNS system, based on their described role.

Answer:

```
The redundancy of the root nameservers across the globe improves its reliability as it prevents single point of failure - when one of the server fails there will be another to handle the request. With regards to the performance, since these clusters are distributed across, when a resolver request to the root nameserver the closest root nameserver to it will accomodate the request reducing the latency traveling from one place to another in case if the root nameserver is hosted only to a single location.
```

3.  Compare and contrast the primary function of a TLD nameserver with that of a Root nameserver, highlighting how their specific roles build upon each other in the resolution chain.

Answer:

```
To state the difference, the TLD nameserver is responsible for storing the list of domain names specific to a Top-level domain and what is their corresnponding Authorative nameservers. While, Root nameservers are responsible for storing list of TLD servers.

The root nameserver returns the TLD server to the recursive resolver in which the TLD server in return responds with the Authorative nameserver completing the
```

4.  If an Authoritative server returns a CNAME record instead of an A record, how does this alter the subsequent steps and the overall efficiency of the recursive resolver's process to obtain the final IP address?

Answer:

```
If the authorative nameserver returns CNAME records the recursive resolver will repeat the resolution again, increasing the time to resolve the domain name since it needs to repeat the process again.
```

5.  Discuss the critical importance of the caching mechanism within the DNS recursive resolver in optimizing the internet experience for users, considering the described process of DNS lookups.

Answer:

```
Caching greatly impacts the performance in which the domain name is getting resolved. The recursive resolver is the one responsible for caching the data, whenever the client request for the same domain, the resolver will just return the cache data without needing to request to other servers greatly impacting the experience of the clients.
```

## Set 3: Knowledge Extension & Inference

1.  Given that DNS translates "domain names to IP address so that users can access this server easily without memorizing its IP address," what might be an inferred challenge for internet users if DNS did not exist or failed frequently?

Answer:

```
It will be harder to navigate the internet entirely.
```

2.  The notes state that TLD servers are owned by "huge companies." Based on this, what might be an inferred reason for this ownership structure, considering the categories of TLDs mentioned?

Answer:

```

```

3.  If "Root nameservers" know where to find servers for Top-Level Domains, what hierarchical implication can be drawn about the overall structure of the internet's naming system?

Answer:

```
The structure of dns is a tree.
```

4.  The note emphasizes that the four DNS server types "need to work in harmony." What can be inferred about the potential impact on user experience if a single type of these servers were to consistently provide incorrect or delayed responses?

Answer:

```
It will greatly impact the resolution of the domain name, delaying the response to the client.
```

5.  Considering the recursive resolver caches results to speed up future transactions, what might be a potential drawback or challenge associated with this caching behavior for website administrators who frequently update their server's IP address?

Answer:

```
If the cache is not updated immediately
```
