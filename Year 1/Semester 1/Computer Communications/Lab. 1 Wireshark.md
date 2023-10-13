#week1 #ComputerCommunications #lab #wireshark
### LO: 
- Be familiar with the Wireshark application interface
- Use Wireshark to capture and view packets

# **Tasks:**
0. **Download Windows CCOM template image on Desktop PC** 
1. **Launch Wireshark** 
	- Password: <mark style="background: #FFF3A3A6;">'student'</mark>
2. **Using Wireshark**
	1. Click <mark style="background: #ADCCFFA6;">'capture' </mark>
	2. Then 'Options...'
	3. ![[Pasted image 20230926114511.png]]
	4. Untick <mark style="background: #ADCCFFA6;">2, 3, 4, 5</mark>
	5. select <mark style="background: #ADCCFFA6;">'ethernet'</mark>
	6. click <mark style="background: #ADCCFFA6;">'start' </mark>
	7. ![[Pasted image 20230926114625.png]]
		- This is all the packets Wireshark is capturing 
	8. <mark style="background: #FF5582A6;">When you are done click </mark><mark style="background: #ADCCFFA6;">capture</mark> <mark style="background: #FF5582A6;">and select</mark> <mark style="background: #ADCCFFA6;">stop</mark> 
		- Or alternatively you can click the red square button
	- ![[Pasted image 20230926114917.png]]
		1. Menus:
			- pulldown menus 
			- when you click one a drop down will appear
			- the ones we use the most will be capture and file menus
		2. Filter
			- can be used to restrict the packets displayed in packets captured 
			- you can filter by packet type for instance 
		3. Packets Captured 
			- also known as packet listing window
			- displays a one-line summary listing of all packets captured on a given interface
		4. Packet Details
			- displays the details about the packet selected in the packet capture window 
		5. Packet Content 
			- displays the contents of selected packet in ASCII and hex 
3. **Capturing Packets**
	1. Open Chrome
	2. Start a Wireshark capture (see task 2)
	3. In URL type http://gaia.cs.umass.edu/wireshark-labs/intro-wireshark-file1.html 
	4. Stop the Wireshark capture 
	5. Filter 'http'
	6. Find and select http://gaia.cs.umass.edu/wireshark-labs/intro-wireshark-file1.html in packets captured window
	7. ![[Pasted image 20230926115804.png]]
	8. Remove the Filter 
4. **Questions**
	- has the content of the 'packets captured' windows changed? if so why?
	- select a packet (any) in 'packet captured' window
		- Look in 'packet details' window. Can you relate what you see in 'packet details' Window to lecture1 'Encapsulation/de-capsulation' processes?
5. **Exit Wireshark by clicking 'file', then 'quit'**
6.  **Reflection and class discussion** 




