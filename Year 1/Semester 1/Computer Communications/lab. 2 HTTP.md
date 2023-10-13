#week2 #lab #ApplicationLayer #HTTP 

## LO: 
- Understand HTTP basic request and response messages
- Understand the formats and contents of different HTTP messages

# Tasks:

Download CCOM Image 
## Task One:
1. Capturing HTTP messages 
	1. open 'Wireshark' and start a capture 
	2. search [http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html]
	3. Stop capture once the get request comes through Wireshark 

ps. 
if you cannot capture HTTP packets, download `HTTP-trace-1` file from MyBeckett, then open it in wireshark 

![[Pasted image 20231003093950.png]]

## Questions:

### Is your browser running HTTP 1.0 or 1.1?

- The browser is running HTTP/1.1
	![[Pasted image 20231003094342.png]]

### What languages (if any) does your browser indicate that it can accept to the server?

- The bowser indicates that it would accept English (Great Britan)
	![[Pasted image 20231003100331.png]]

### What is the IP address of your computer?

- The IP from my computer is 172.16.1.247
	![[Pasted image 20231003094308.png]]

### What Version of  HTTP is the server running?

- The server is running HTTP/1.1
	![[Pasted image 20231003094457.png]]
	![[Pasted image 20231003094833.png]]

### What is the IP address of the server?

- 128.119.245.12
	![[Pasted image 20231003094900.png]]
	![[Pasted image 20231003094909.png]]

### What is the status code returned from the server to your browser

- 200
	![[Pasted image 20231003094900.png]]
	![[Pasted image 20231003094940.png]]

### When the HTML file that you are retrieving was last modified at the server?

- Tue, 03 Oct 2023 5:59:02 GMT
	![[Pasted image 20231003095127.png]]

### How many bytes of content are being returned to your browser

- 128 bytes
	![[Pasted image 20231003095212.png]]



# Task 2 - HTTP conditional GET request and response messages

1. Clear your Chrome browser cache
	1. click top-right corner
	2. more tools
	3. clear browser data

2. Launch Wireshark and capture
3. [http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html](http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html)
4. Once your browser displayed the page, refresh your browser
5. stop the capture

ps. 
if this cannot capture HTTP packets download `HTTP-trace-2` file from my Beckett

6. Filter the Packets for `http`

![[Pasted image 20231003104748.png]]
## Questions

### Select the first request message (‘GET’) in packet capture window. Do you see “If-Modified Since”” line in the HTTP GET?

- No
- ![[Pasted image 20231003104955.png]]
### Has the server returned the contents of the file that was requested by your browser?

yes
### Select the second request message (‘GET’) in packet capture window. Do you see “If-Modified-Since” line in the HTTP GET? If yes, what information is listed after If-Modified Since?

- Yes, It says if modified from Tue, 03, Oct 2023 05:59:02 GMT
	![[Pasted image 20231003104915.png]]

### What is the HTTP status code and phrase returned from the server in response to second HTTP GET message? 

```http
HTTP/1.1 304 Not Modified
```
![[Pasted image 20231003105215.png]]
- 304 (Not Modified)
### Did the server explicitly return the contents of the file?

No. It just used the cache from the previous GET request 

# Task 3 - Downloading a Web page with embedded objects

1. Open chrome 
2. Start a new capture (Wireshark)
3. search `http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html`
4. stop the capture

ps. 
if you cannot capture, download `http-trace3`

	![[Pasted image 20231003110636.png]]

## Questions
### How many HTTP request messages did your browser send?

![[Pasted image 20231003110656.png]]
Three requests were sent:
1. GET /wireshark-labs/HTTP-wireshark-file4.html 
2. GET /pearson.png
3. GET /8E_cover_small.jpg
### To which Internet addresses were these GET requests sent?

The GET requests came from:
- http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html
- http://gaia.cs.umass.edu/pearson.png
- http://kurose.cslash.net/8E_cover_small.jpg

![[Pasted image 20231003110858.png]]![[Pasted image 20231003110937.png]]
![[Pasted image 20231003111053.png]]
![[Pasted image 20231003111104.png]]
### Can you tell whether your browser downloaded the two images from one or two websites? Explain 

The browser downloaded the images from two sites as there was a separate GET request from each image which includes two different sites.
# Task 4 - HTTP Authentication 

Next you will try to download a page from a web site that is password-protected and examine the sequence of HTTP messages.

1. clear cache
2. start capture
3. `[http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wiresharkfile5.html](http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wiresharkfile5.html)`
4. Enter the login details and sign in 
	Username: `wireshark-students`
	Password: `network`
5. Stop the capture

ps.
if no capture download `HTTP-trace-4`

6. Filter the packets `http`

![[Pasted image 20231003111804.png]] (what I found vs trace4)

![[Pasted image 20231003155905.png]]
## Questions
### What is response status code and phrase to the initial to first HTTP GET message from your browser

401 (unauthorised)
![[Pasted image 20231003155942.png]]
### Can you see any field sent in the second HTTP GET message? Explain
- You can see the username and password within the get packet 
	![[Pasted image 20231003153812.png]]

### What is response code and phrase to the second HTTP GET message from your browser?
- 200 (OK)
	![[Pasted image 20231003160004.png]]