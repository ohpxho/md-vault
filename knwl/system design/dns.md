# DNS Notes - Dec 06, 2025

- Stands for `Domain Name System`
- It is the phonebook of the internet.
- It maps a domain name (E.g. example.com) into an IP address.
- It translates domain names to IP address so that users can access this server easily without memorizing its IP address.

## Types of DNS servers

1. Recursive resolvers
2. Root nameservers
3. TLD nameservers
4. Authorative nameservers

- These 4 needs to work in harmony to deliver the right address to a client.

## Process

1. Client query a domain name
2. DNS recursor receives the query
3. a. DNS responds with a cache data
   b. DNS query a root nameserver
4. Root nameserver responds to resolver with the dedicated TLD server
5. TLD server respond to resolver with the authorative server
6. Authorative server returns with DNS records to the resolver
7. DNS recursive resolver return the address to the client and caches the result

`!!! If the authorative server returns with a CNAME records, the recursive resolver will have to perform a whole new DNS lookup !!!`

## DNS Resolver (DNS recursive resolver)

- A server that manages the `name to address` translation.
- Acts as the middleman between the client and the DNS nameserver
- It caches past results so that whenever you visit the site again it will return the cache data making the transaction faster.
- These servers are hosted by: ISP, router, or public DNS providers (Google DNS(8.8.8.8), Cloudflare DNS(1.1.1.1), etc.)

## Root Name Server

- It knows where to find server responsible for Top-Level Domains(TLDs) like `.com`, `.net`
- It stores a list of all TLDs and their corresponding servers
- There are 13 root **server clusters** worlwide, not just one server. (Total of servers is around 600, located in various part of the world)

## TLD Server

- It holds a list of domain names and their dedicated authorative server under a specific extension (E.g. for .com, there is a TLD server specific for that).
- This servers are owned by huge companies such as: Verisign (.com), etc.
- IANA breaks up the TLD servers into two main groups:
  1. Generic top-level domains: .com, .org (not country specific)
  2. Country code top-level domains: .us, .pf (specific to a countru or state)

## Authorative nameserver

- This is the last step and contains the informatino specific to the domain name it serves.
