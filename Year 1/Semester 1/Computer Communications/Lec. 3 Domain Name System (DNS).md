LO:
- Describe the concept and purpose of name system 
- Describe DNS name space and servers
- Explain DNS messages

## Name System 
- Unique IP addresses, identify nodes in a TCP/IP network 
- People prefer to use names instead of IP addresses (makes it easier to remember)
	- e.g. google.com (instead of 8.8.8.8)
- Hence, there is need for a system that can map a map to an address
- Name system maintains a collection of binding of names to values
	- provides mapping between hostnames and equivalent IP addresses

## Domain Name System (DNS)
- DNS is a distributed hierarchical database
- Domain names are hierarchical 
- Each name consists of a number of parts separated by a dot 
- **Domain Name Hierarchy** ![[Pasted image 20231010125953.png]]![[Lec. 3 Domain Name System (DNS)-20231010120104080.webp]]

## Local DNS Server (default name server)
- Responds to local DNS queries 
- Acts as proxy on behalf of local hosts, forwards query into hierarchy![[Pasted image 20231010130247.png]]

## DNS Database Entries (Records)
- DNS database stores resource records (RRs)
- Each record consists of
	- (name, value, type, TTL)

- Type specifies how the value to be interpreted
	- A - Address
		- name is hostname
		- value is IP address
	- NS - Name Server
		- Identifies authoritative server
	- CNAM - Canonical Name
		- It is used to define aliases 
	- MX - Mail Exchange

## DNS Messages

Messages >
- Query 
- Response
![[Pasted image 20231010131535.png]]![[Pasted image 20231010131726.png]]

### Message Header

![[Pasted image 20231010131617.png]]


# DNS Name Resolution 

- User opens the web browser and enters address:
	- `http://go.Microsoft.com`
- The DNS client software called resolver (a program), sends a query with the above hostname to local DNS server
- If the Local DNS server can resolve the query, it responds with an IP address mapping to the hostname 
- If the DNS server is not the authority for the domain and cannot resolve the query. The query would be propagated to higher DNS servers.
- If local DNS server is not the authority for the domain and cannot resolve the query. The query would be propagated to higher DNS servers
- Eventually, the client receives an IP address that corresponds to the hostname

## Authoritative 
- Authoritative servers store and manage the official DNS records for domains, ensuring accurate and up to date information, while non-authoritative servers act as intermediaries, forwarding and caching DNS queries to improve performance and reduce latency 
# Recursive and Iterative Resolutions
- Recursive query 
	- The client expects the name server to provide an answer to the query 
- Iterative (iterated ) query 
	- If the name server cannot resolve the query, it returns the address of server that it thinks can resolve it
	- The client is responsible for repeating the query until it is resolved

## DNS Caching

- Once the name server (local DNS sever for instance) learns a mapping, it caches the mapping 
- If an entry is in the cache, the query does not have to propagate to other servers. It is resolved locally
- Caching speeds up name resolution 
- Time-to-Live (TTL)
	- Cache entries which timeout (expired TTL) are removed

![[Pasted image 20231010133311.png]]
![[Pasted image 20231010133328.png]]
![[Lec. 3 Domain Name System (DNS)-20231010123351239.webp]]
![[Lec. 3 Domain Name System (DNS)-20231010123359131.webp]]
![[Pasted image 20231010133406.png]]








