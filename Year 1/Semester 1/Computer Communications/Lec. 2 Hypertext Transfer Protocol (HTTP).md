#week2 #ComputerCommunications #Lecture #Protocols #HTTP #ApplicationLayer 

### LO:
- Describe client and server model 
- Explain HTTP and different types of HTTP messages 
- Explain cookies and their applications in HTTP
- Explain Web caching 

## Client and Server Model 

- Client is a program running on computer that requests a service from a server 
	- Client is usually invoked by an end-user application
- Server in general, is a program running on another computer (remove machine) providing service to clients 
	- waits for clients requests and replies to requests as received 

 ![[Pasted image 20230929114043.png]]

# HTTP

## HTTP Protocol 

- Application layer protocol 
- Client and server model protocol 
	- Client (HTTP client) - Web browser running on your device
		- Uses HTTP to send requests to the Web server
	- Web server (HTTP server) - uses HTTP to respond to client
- Uses #TCP as transport protocol 

## HTTP Messages 

![[Pasted image 20230929115518.png]]

## HTTP Request and Response Messages

![[Pasted image 20230929115552.png]]

## HTTP Request Message General Format

![[Pasted image 20230929115616.png]]

## HTTP Request Line Format

![[Pasted image 20230929115634.png]]

## Some of HTTP Request Line Methods 

| Method  | Action                                                            |
|:------- |:----------------------------------------------------------------- |
| GET     | Requests a document from the server                               |
| HEAD    | Requests information about a document but not the document itself |
| POST    | Sends some information from the client to the server              |
| PUT     | Sends a document from the server to the client                    |
| TRACE   | Echoes the incoming request                                       |
| CONNECT | Reserved                                                          |
| DELETE  | Remove the Web page                                               |
| OPTIONs | Enquires about available options                                                                   |

## HTTP Header Format 

![[Pasted image 20230929120048.png]]

## Some of HTTP Request Header Names 

| Header            | Description                                     |
|:----------------- |:----------------------------------------------- |
| User-agent        | Identifies the client program                   |
| Accept            | Shows the media format the client can accept    |
| Accept-charset    | Shows the character set the client can accept   |
| Accept-encoding   | Shows the encoding scheme the client can accept |
| Accept-language   | Shows the language the client can accept        |
| Authorisation     | Shoes what permissions the client has           |
| Host              | Shows the host and port number of the client    |
| Date              | Shows the current date                          |
| Upgrade           | Specifies the preferred communications protocol |
| Cookie            | Returns the cookie to the server                |
| If-Modified-Since | Returns the cookie to the server                                                |

## HTTP Request Message General Format

![[Pasted image 20230929120625.png]]

## An Example of a HTTP Request Message 

![[Pasted image 20230929120651.png]]

## HTTP Response Message 

![[Pasted image 20230929120715.png]]

## HTTP Status Line Format 

![[Pasted image 20230929120750.png]]

## Status Codes and Phrases

![[Pasted image 20230929120809.png]]

## An Example of HTTP Response Message

![[Pasted image 20230929120856.png]]

## HTTP Request and Response Messages

![[Pasted image 20230929120926.png]]

## HTTP Connections

- HTTP client uses TCP to set up a connection to a server 
	- Creates a socket to the server 
	- Uses port 80 for the HTTP Protocol 
- Once the server accepts TCP connection and the connection is set IP
- HTTP messages can be exchanged between the client (browser) and Web Server
- TCP connection is then Closed 

## Cookies 

- Allows Web sites to keep track of users
- Can be used for 
	- Authorization
	- Shopping carts
	- user session state

![[Pasted image 20230929114928.png]]

## Web Caching 

- Web Cashing is used by the browser to improve the performance of accessing Web pages
- When a web page is downloaded a copy is kept in the cache for future use and avoid sending a request to the web server
	- Allows for quicker loading times 
	- Stops the same packet being sent every time you load the same page
![[Pasted image 20230929115153.png]]

