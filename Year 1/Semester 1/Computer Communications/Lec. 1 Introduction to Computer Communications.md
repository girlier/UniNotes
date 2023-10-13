#week1 #ComputerCommunications #Lecture #TCP/IP #OSI #Protocols #Encapsulation
### LO:
- Describe the main components of computer communication systems
- Describe the importance of protocols for successfully data
communication
- Explain the concept of multi-layering in computer communications and
networking
- Describe OSI and TCP/IP reference models
- Describe the functionality of each layer in the TCP/IP model
- Explain encapsulation and de-encapsulation processes

## Basic Communications 
![[Pasted image 20230926120350.png]]

## Computer Network Components 
![[Pasted image 20230926120433.png]]

## Some of Requirements of Successful Computer Communications
1. Identifying sender and receiver 
	- Addressing
2. Sharing the transmission system between nodes
	- Media access control 
3. Messaging formatting and encapsulation 
	- Grouping sequence of bits into complete messages
4. Encoding bits onto the wire that can be understood by the reciver 
5. Confirmation 
	- acknowledgement 
6. Error control
	- Errors in the transmission system 
7. Flow control 

## Protocols *(network protocols/ computer communications protocols)*
This is a set of rules that govern data communications
**example 1:**
![[Pasted image 20230926120838.png]]

## Layered Architecture
- Computer communications and networks are very complex
- There are many different communications tasks
	- There is a natural order in which the tasks need to be done
- Computer communications can be considerably simplified if one breaks
	them into several layers.
- This introduces the idea of “layering”
- Makes it easier to design, implement and test each protocol
- Modularized
	- Allows to perform updates and make changes
- Promotes standards to be defined to regulate and guide what
each layer must do.

## The OSI Reference Model 
- The OSI Reference Model aims to encourage the open interconnection of
computer systems
- It is a multi-layered model for facilitating the transfer of information on a
network
- It is a conceptual framework specifying the network functions

## Seven Layers of OSI Reference Model 

- ![[Pasted image 20230926121201.png]]

## TCP/IP Model 

- ![[Pasted image 20230926121224.png]]

## Functions of Layers 
- **Physical Layer** - Concerned with the transmission of the bit stream over the physical medium
	- Type of transmission media
	- Mechanical and electrical specification of the interface
	- How cable is attached to the network card
	- Encoding of bit stream
	- Transmission mode

- **Data Link Layer**
	- Packaging data (bits) into logical structure
		- Framing and frame sequencing
	- Adding MAC addresses to the frame
		- Physical addressing
	- Medium access control ‘if the transmission medium is a shared Medium’
	- Error notification

- **Network Layer** - Provides upper layers with independence from the data transmission and switching technologies used
	- Adding logical addresses (IP addresses) to datagram
	- Path selection
		- Routing

- **Transport Layer** - Provides reliable and transparent transfer of
data between end points
	- Establishing, maintaining, and terminating connections
	- Data segmentation and reassembling
	- Error control
	- Flow control

- **Application Layer**
	- Provides network services for users applications

## Encapsulation 
- If a computer wants to send data to another computer, the data must be packaged by a process called encapsulation
- Encapsulation wraps data with the necessary information before it is transmitted

### Encapsulation/De-Encapsulation
![[Pasted image 20230926121716.png]]

**Letter analogy** - Think about a letter being sent (Encapsulation); a letter being recived (De-encapsulation)
## Names of Data Units at Each Layer

| Name of Layer     | Units   |
| ----------------- | ------- |
| Application Layer | Data    |
| Transport Layer   | Segments |
| Network Layer     | Packets |
| Data Link Layer   | Frames  |
| Physical Layer    | Bits        |
