LO:
- Use `nslookup` to perform DNS queries
- Use Wireshark to capture, analyse DNS query and response messages

Download `CCOM` template image on Desktop PC.

# Task. 
`Bottom PC`

**1. Using `nslookup`**
	1. Login to bottom PC.
	2. Open `CMD`
	3. type `nslookup `
	4. What is the default DNS server used by your PC? ![[Pasted image 20231010105558.png]]
		- dns1.as42689.net
	5. Type `?` ![[Pasted image 20231010105631.png]]
	6. Type `www.leedsbeckett.ac.uk` ![[Pasted image 20231010105708.png]]
		- `nslookup` provides two main pieces of information
			- The name and `IP` address of the `DNS` server that provided the answer
			- The answer itself, the domain name and `IP address` of the domain name
		- `nslookup` uses type `A` query and sends to the query to the default DNS sever. 
			- We can use `-type` option to specify how the query should be interpreted
	6. Type `exit` 
	7. Type `nslookup -type=NS www.leedsbeckett.ac.uk` to find the name of the authoritative DNS for `www.leedsbeckett.ac.uk` ![[Pasted image 20231010110330.png]]
	8.  DNS for:
		1. IPs of `amazon.co.uk`
			1. `54.239.33.58`
			2. `178.236.7.220`
			3. `54.239.34.171`
		2. Authoritative DNS server(s) for `amazon.co.uk` 
			1. `ns1.amzndns.net` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.net` <mark style="background: #FF5582A6;">(auth)</mark>
			2. `ns1.amzndns.com` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.com` <mark style="background: #FF5582A6;">(auth)</mark>
			3. `ns2.amzndns.com` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.com` <mark style="background: #FF5582A6;">(auth)</mark>
			4. `ns2.amzndns.net` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.net` <mark style="background: #FF5582A6;">(auth)</mark>
			5. `ns1.amzndns.co.uk` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.co.uk` <mark style="background: #FF5582A6;">(auth)</mark>
			6. `ns1.amzndns.org` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.org` <mark style="background: #FF5582A6;">(auth)</mark>
			7. `ns2.amzndns.co.uk`<mark style="background: #BBFABBA6;"> (non)</mark>
				- `g-ns1.amzndns.co.uk` <mark style="background: #FF5582A6;">(auth)</mark>
			8. `ns2.amzndns.org` <mark style="background: #BBFABBA6;">(non)</mark>
				- `g-ns1.amzndns.org` <mark style="background: #FF5582A6;">(auth)</mark>
		3. Authoritative DNS server(s) for `google.co.uk`
			1. `ns4.google.com` <mark style="background: #BBFABBA6;">(non)</mark>
				- `ns1.google.com` <mark style="background: #FF5582A6;">(auth)</mark>
			2. `ns3.google.com` <mark style="background: #BBFABBA6;">(non)</mark>
				- `ns1.google.com` <mark style="background: #FF5582A6;">(auth)</mark>
			3. `ns1.google.com` <mark style="background: #FF5582A6;">(auth)</mark>
			4. `ns2.google.com` <mark style="background: #BBFABBA6;">(non)</mark>
				- `ns1.google.com` <mark style="background: #FF5582A6;">(auth)</mark>
		1. Authoritative DNS server(s) for `ox.au.uk`
			1. `ns2.parkingcrew.net` <mark style="background: #BBFABBA6;">(non)</mark>
				- `ns-1403.awsdns-47.org` <mark style="background: #FF5582A6;">(auth)</mark>
			2. `ns1.parkingcrew.net` <mark style="background: #BBFABBA6;">(non)</mark>
				- `ns-1403.awsdns-47.org` <mark style="background: #FF5582A6;">(auth)</mark>
		1. Authoritative DNS server(s) for `www.leedsbeckett.ac.uk`
			1. `ns4.js.net` <mark style="background: #BBFABBA6;">(non)</mark>
			2. `dns5.leedsbeckett.ac.uk` <mark style="background: #BBFABBA6;">(non)</mark>
			3. `dns7.leedsbeckett.ac.uk` <mark style="background: #BBFABBA6;">(non)</mark>
			4. `dns4.leedsbeckett.ac.uk` <mark style="background: #BBFABBA6;">(non)</mark>
			5. `dns6.leedsbeckett.ac.uk` <mark style="background: #BBFABBA6;">(non)</mark>
		2. Leeds Beckett University mail server(s). 
			1. `ns-1903.awsdns-45.co.uk` ![[Pasted image 20231010130955.png]]

**2. Capturing DNS messages**
	1. Use `Desktop PC` `CCOM` template
	2. open `cmd`
	3. type ipconfig/all ![[Lab. 3 Domain Name System (DNS)-20231010145406287.webp]]

| IP4 address                | 192.168.204.171    |
|:-------------------------- |:--- |
| MAC address                | C8-D9-D2-26-E8-1D     |
| Default gateway IP address | 192.168.204.1    |
| Network (subnet) mask      | 255.255.255.0    |
| DNS server IP address                           | 192.168.208.51    |

Displaying DNS cache on your PC. 
	1. type `ipconfig/displaydns` 
	 ![[Pasted image 20231010113229.png]]
Clearing DNS cache on your PC.
	1. type `ipconfig/flushdns`![[Lab. 3 Domain Name System (DNS)-20231010103443683.webp]]

Make sure DNS cache on your PC is empty and leave the CMD window open
1. Start Wireshark, click `Options` > `Ethernet`
2. In `CMD` type `nslookup www.icann.org` 
3. Then stop Wireshark 
	- If you did not get that download `DNS-trace-file`
4. Filter Wireshark `dns`
	1. Select `www.icann.org` DNS query packet in Packets Captured
5. Questions
	1. Is the DNS query sent over UDP or TCP?
		1. `UDP` *DNS ALWAYS USES UDP*![[Lab. 3 Domain Name System (DNS)-20231010103912863.webp]]
	2. What is the destination IP address of DNS query? 
		1.  `192.168.208.51` ![[Lab. 3 Domain Name System (DNS)-20231010104058389.webp]]
	3. Is this same as IP address of your local DNS server? If so, explain why?
		- No, this is because the DNS server's IP is used for name resolution and your own IP address is used to identify your device on the network. 
		 
	4.  It is an ‘Iterative’ or ‘Recursive’ DNS query? 
		 - Recursive ![[Pasted image 20231010132607.png]]
	    
	5. How many ‘queries’ are in the DNS query? 
		- 1![[Lab. 3 Domain Name System (DNS)-20231010154514634.webp]] 
	    
	6. What is the DNS query Type?  Explain.
		- The  query type from the client was `A` (Address) record query 
			- Translates a domain name into an IPv4 Address
	    
	7. How many ‘answers’ are in the DNS query? 
		1. 2 Answers 
			1. Response from the `A` query ![[Lab. 3 Domain Name System (DNS)-20231010154914307.webp]]
	    
	8. Should there be any ‘answers’ in the DNS query, if not why not? 
		1. Because it is a query and there is no response in a query ![[Lab. 3 Domain Name System (DNS)-20231010154745402.webp]]