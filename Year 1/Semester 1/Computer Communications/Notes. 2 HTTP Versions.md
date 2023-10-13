#week2 #TCP/IP #Protocols #HTTP #ExtraReading

## HTTP Versions
| Version  | Year Introduced | Current status |
|:-------- |:--------------- |:-------------- |
| HTTP/0.9 | 1991            | Obsolete       |
| HTTP/1.0 | 1996            | Obsolete       |
| HTTP/1.1 | 1997            | Standard       |
| HTTP/2   | 2015            | Standard       |
| HTTP/3   | 2022            | Standard               |

### HTTP/0.9

- First documented version of HTTP written in plain text
- > 700 words long
- Only supports GET method 
	- allows clients to retrieve HTML documents but not any other file format 
	- doesn't even allow information upload
- Request nature: Single line (method + path for requested document) 
- Connection nature: terminated immediately after the response
- No HTTP headers 
	- No status/error codes
	- No URLS
	- No versioning 

```HTTP
$> telnet example.com 80

(Connection 1 Establishment - TCP Three-Way Handshake)
	Connected to xxx.xxx.xxx.xxx

(Request)
	GET /my-page.html

(Responce in hypertext)
	<HTML>
		A very simple HTML page
	</HTML>

(Connection 1 Closed - TCP Teardown)
```

### HTTP/1.0 
**http/1.0-draft**
- 1992
- new document was written to specify the evolution of the basic protocol
- supported full GET request that included the client HTTP version 
- first of many unofficial HTTP/1.0 drafts that lead to the final work on HTTP/1.0.

**Full release**
- 1996
- RFC 1945 was published as a final HTTP/1.0 revision of what had been used in previous 4 years from the draft
- In early 1996, developers started to include unofficial extensions into their products by using drafts of the HTTP/1.1
- Added:
	- HEAD and POST
	- Status and error codes
	- header
	- support for different filetypes

Example
```HTTP
GET /index.html HTTP/1.O
User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)
```

```http
200 OK
Date: Sun, 01 Jan 1995 12:01:00 GMT
Server: CERN/3.0 libwww/2.17
Content-Type: text/html

<html>
	Simple Hypertext 
</html>
```

Example 2
```http
GET /logo.gif HTTP/1.0
User-Agent: NCSA_Mosaic/2.0 (Windows 3.1)
```

```http
Date: Sun, 01 Jan 1995 12:01:00 GMT
Server: CERN/3.0 libwww/2.17
Content-Type: text/gif

<encoded data of logo.gif>
```

### HTTP/1.1
- 1997
- In 1996 one web hosting company reported that over 40% of browsers in use on the internet used the new HTTP/1.1 header "Host" to enable virtual hosting
- 1999, RFC 2616 was released to include all improvements and updates based on previous (obsolete HTTP/1.1 specifications)
- added:
	- cache controls
	- Content Negotiations
	- Host header
		- able to support servers hosted on different domains but located at the same IP address
	- Reuse of a HTTP Connection 
	- New HTTP request methods
	- supports for many new HTTP headers

example:
```http
GET /index.html HTTP/1.1
Host: www.example.re
User-Agent: Mozilla/5.0 (Windows; U; Windows NT 5.0; en-US; rv:1.1)
Accept: text/html
Accept-Language: en-US, en; q=0.5
Accept-Encoding: gzip, deflate
```

``` http
200 OK
Server: Apache
Date: Thu, 01 Jan 1998 12:01:00 GMT
Connection: Keep-Alive
Keep-Alive: timeout=5, max=500
Content-Encoding: gzip
Content-Type: text/html; charset=UTF-8
Last-Modified: Mon, 29 Dec 1997 12:15:00 GMT
Transfer-Encoding: chunked

<html>
	Simple HTML 
</html>
```

**2014 updates to HTTP/1.1**
In June 2014, the HTTP Working Group released an updated six-part HTTP/1.1 specification obsoleting RFC 2616

| RFC  | HTTP/1.1: Addition         |
|:---- |:-------------------------- |
| 7230 | Message Syntax and Routing |
| 7231 | Semantics and Content      |
| 7232 | Conditional Request        |
| 7233 | Range Requests             |
| 7234 | Caching                    |
| 7235 | Authentication             |

### HTTP/2
- 2015
- support from several popular internet browsers and web server software
- extended the usage of persistent connections by multiplexing many concurrent requests/responses through a single TCP/IP connection
- it's a binary protocol that cannot be written or read manually
- introduces HTTP header field Compression and supports multiple concurrent data exchanges on a single HTTP Connection.
- Multiplexing allows for multiple HTTP request to be in progress at one time. 
	- HTTP/2 does not make use of multiple connections
		- all of HTTP requests are made concurrently using a single one HTTP Connection
		- utilizing network recourses
- Optimized for HTTP transport
- all other features from 1.1 are supported 

- HTTP/2 was quickly adopted
	- does not require changes to server-side applications or websites
	- no loss of information or modification of the HTTP headers
	- the bandwidth conservation led to cost savings 
		- particularly for high traffic websites 

HTTP/1.1 is not obsolete
- backwards compatible
- method of data transport is optimized
- the result is a more optimized protocol with better performance, and fewer workarounds 

**Google SPDY**
- to cope with increased number of HTTP requests with HTTP/1.1
	- google implemented SPDY (speedy) protocol. 
		- made to reduce webpage load latency and improve security 
		- when SPDY started to show improvement over HTTP/1.1
			- it was adopted by other browsers and the notion of HTTP/2 was introduced
- SPDY was deprecated and HTTP/2 was used instead

### HTTP/3
- 2020
- currently a IETF draft
	- already supported by majority of web browsers 
- does not use TCP/IP connections but QUIC + UDP

![[Pasted image 20230929180734.png]]
## Request for comments
**RFC** is a publication services from the principle technical development and standards-setting bodies for the Internet 
Authorised by individuals or groups of engineers and computer scientists 

Example
https://datatracker.ietf.org/doc/html/rfc7230?utm_source=localhost%3A8080