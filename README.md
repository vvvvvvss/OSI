# OSI
The Open Systems Interconnection (OSI) model describes seven layers that computer systems use to communicate over a network.    
![OSIModel drawio (1)](https://github.com/user-attachments/assets/7808d1d1-292d-45f1-a3c6-c5857ed6d86e)

Recieving data - bottom up approach   
Transmitting data - top down approach

## 7. Application Layer
The application layer is used by end-user software such as web browsers and email clients.
It provides protocols that allow software to send and receive information and present meaningful data to users. 
A few examples of application layer protocols are the Hypertext Transfer Protocol (HTTP), File Transfer Protocol (FTP), 
Post Office Protocol (POP), Simple Mail Transfer Protocol (SMTP), and Domain Name System (DNS).

## 6. Presentation Layer

The presentation layer prepares data for the application layer.
It defines how two devices should encode, encrypt, and compress data so it is received correctly on the other end. 
The presentation layer takes any data transmitted by the application layer and prepares it for transmission over the session layer.

## 5. Session Layer

The session layer creates communication channels, called sessions, between devices. 
It is responsible for opening sessions, ensuring they remain open and functional while data is being transferred, and closing them when communication ends. 
The session layer can also set checkpoints during a data transfer—if the session is interrupted, devices can resume data transfer from the last checkpoint.

## 4.Transport Layer

The transport layer takes data transferred in the session layer and breaks it into “segments” on the transmitting end. 
It is responsible for reassembling the segments on the receiving end, turning it back into data that can be used by the session layer. 
The transport layer carries out flow control, sending data at a rate that matches the connection speed of the receiving device, and error control, checking if data was received incorrectly and if not, requesting it again.

## 3.Network Layer

The network layer has two main functions. One is breaking up segments into network packets, and reassembling the packets on the receiving end. 
The other is routing packets by discovering the best path across a physical network. The network layer uses network addresses (typically Internet Protocol addresses) to route packets to a destination node.

## 2.Data Link Layer

The data link layer establishes and terminates a connection between two physically-connected nodes on a network. 
It breaks up packets into frames and sends them from source to destination. 
This layer is composed of two parts—Logical Link Control (LLC), which identifies network protocols, performs error checking and synchronizes frames, 
and Media Access Control (MAC) which uses MAC addresses to connect devices and define permissions to transmit and receive data.

## 1.Physical Layer

The physical layer is responsible for the physical cable or wireless connection between network nodes. 
It defines the connector, the electrical cable or wireless technology connecting the devices, and is responsible for transmission of the raw data, 
which is simply a series of 0s and 1s, while taking care of bit rate control.

# SWITCH
Switches are networking devices operating at layer 2 or a data link layer of the OSI model. 
They connect devices in a network and use packet switching to send, receive or forward data packets or data frames over the network.
A switch has many ports, to which computers are plugged in. 
When a data frame arrives at any port of a network switch, it examines the destination address, performs necessary checks and sends the frame to the corresponding device(s). 
It supports unicast, multicast as well as broadcast communications.
Switching in IT and computer networking is the transfer of data packets, or blocks of data, through a network switch. Switches transfer data from source ports on devices such as computers to destination ports on devices such as routers.
# ROUTER
Routers are networking devices operating at layer 3 or a network layer of the OSI model. 
They are responsible for receiving, analysing, and forwarding data packets among the connected computer networks. 
When a data packet arrives, the router inspects the destination address, consults its routing tables to decide the optimal route and then transfers the packet along this route.
# HUB
Hubs are networking devices operating at a physical layer of the OSI model that are used to connect multiple devices in a network. 
They are generally used to connect computers in a LAN.
A hub has many ports in it. A computer which intends to be connected to the network is plugged in to one of these ports. 
When a data frame arrives at a port, it is broadcast to every other port, without considering whether it is destined for a particular destination device or not.
A hub operates in the physical layer of the OSI model.
A hub cannot filter data. It is a non-intelligent network device that sends message to all ports.
It primarily broadcasts messages. So, the collision domain of all nodes connected through the hub stays one.


# HANDSHAKES
It is protocal used to start a connection between two more decices
## Two-Way Handshake
The two-way handshake is a simple protocol to create a connection between two parties that want to communicate. 
In order to do that, this protocol uses synchronization (SYN) and acknowledgment (ACK) messages.
SYN message requires a connection and informs the other party of a sequence number to control the data exchange. 
In practice, the TCP sequence number is a counter of bytes passing on a particular stream. 
ACK messages, in turn, are employed to confirm receipt (using the sequence number) of incoming messages.

To accomplish the two-way handshaking considering a client/server model, the client sends an SYN message to the server with a sequence number X. 
Then, the server should acknowledge (ACK) the SYN message, providing another sequence number Y and establishing the connection. 
Thus, sequence number X will acknowledge messages from the client to the server, while sequence number Y will acknowledge messages from the server to the client.

The following figure depicts the previously described two-way handshake process:
![image](https://github.com/user-attachments/assets/a16babd5-1047-40cd-8d95-65bd3e7f444e)

#### Problem with two-way handshake
Particularly, the two-way handshake presents potential problems when the ACK message from the server delays too much. 
Thus, if a connection timeout occurs, the client sends another SYN message with a new sequence number (Z, for example) to the server. 
However, if the server previously sent an ACK (which is delayed), it’ll discard this new SYN message. 
The client, in turn, receives the delayed ACK and assumes that it refers to the last sent SYN message. 
Here’s where the error happens: the client will send messages with the sequence number Z, while the server expects messages following the sequence number X.

## Three-Way Handshake
Like two-way handshaking, three-way handshaking also establishes connections between two parties using SYN and ACK messages. 
However, besides providing their sequence numbers, the server and client acknowledge the sequence numbers from each other. 
This sequence number acknowledgment avoids the occurrence of SYN duplication errors.

So, let’s consider that a client wants to communicate with a server that employs the three-way handshaking protocol. 
First, the client sends an SYN message with your sequence number (X) to the server. 
The server replies with an SYN-ACK containing its sequence (Y) number and acknowledging the client’s sequence number (X). 
After that, the client sends an ACK message to confirm the server’s sequence number (Y), finally establishing the connection.

The following figure demonstrates the presented three-way handshake process:
![image](https://github.com/user-attachments/assets/116e5b48-da54-48bd-97a6-da71803df242)



Other references: https://youtu.be/vv4y_uOneC0?si=hI5W-QstV6OAKLN4
https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/
