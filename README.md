# Computer-Networks
Lecture notes on Computer Networks 

By Malika Rustamova

## Learning roadmap
- [ ] START HERE: [Naso Academy CN playlist](https://youtube.com/playlist?list=PLBlnK6fEyqRgMCUAG0XRw78UA8qnv6jEx&feature=shares)


## Contents
- [Introduction to Computer Network](#introduction-to-computer-network)

## Introduction to Computer Network
- Computer Network is a set of nodes connected by communication links
- The aim of the computer network is the sharing of resources among various devices.

### Internet
- The Internet is a computer network that interconnects billions of computing devices 
throughout the world.
All communication activity in Internet governed by ***protocols***

### Network edge
**Hosts** - clients and servers
<br> <img src="images./edge.jpg" width=400>

**Access network, physical media** - wired, wireless communication links
<br> <img src="images./media.jpg" width=400>

**Network Core** - interconnected routers, network of networks
<br> <img src="images./core.jpg" width=400>

***Routing and Forwarding*** are the two key network-core functions.

***Packet switching*** is defined as the connectionless network where the messages are divided and grouped together and this is known as a packet. Each packet is routed from the source to the destination as individual packets. 
***Circuit switching*** is referred to as the technology of data transfer that utilizes sending messages from one point to another. This involves sending messages from the receiver to the sender and back simultaneously


## Performance: delays, loss and throughput
A network delay is the amount of time required for one packet to go from its source to a destination. It is also called the end-to-end delay, and it comprises the following 4 types of delays:

- Transmission delay
- Propagation delay
- Queuing delay
- Processing delay

***1. Transmission delay*** - the time taken to transmit a packet from the host to the transmission medium. 
This delay depends upon the following factors:

- If there are multiple active sessions, the delay will become significant.
- Increasing bandwidth decreases transmission delay.
- MAC protocol largely influences the delay if the link is shared among multiple devices.
- Sending and receiving a packet involves a context switch in the operating system, which takes a finite time.

Dtrans = L/R (L: packet length (bits), R: link bandwidth (bps))

***2. Propagation delay*** - the amount of time a bit on the link needs to travel from the source to the destination.
Factors affecting propagation delay:  

- Distance – It takes more time to reach the destination if the distance of the medium is longer. 
- Speed – If the velocity(speed) of the signal is higher, the packet will be received faster.  

Dprop = d/s (d: length of physical link, s: propagation speed (~2x108 m/sec))

***3. Queueing delay*** - the amount of time it waits in queue before being processed is called queueing delay. 
This delay depends on the following factors:

- The number of packets arriving in a short time interval.
- The transmission capacity.
- The size of the queue.

***4. Processing delay*** - the time taken by a processor to process the data packet.
- It depends on the speed of the processor.

Ttotal = Dtrans + Dprop + Dqueue + Dpro
<br> <img src="images./delays.jpg" width=400>

### Internet Protocol Stacks

**Layering** - decomposing the problem into more managable components.

There are five layers in the internet protocol stack
- **Application layer** - responsible for communication between applications running on two different end systems. The protocols used at the application layer include:
  - ((HTTP): for transferring HTML web documents,(FTP): for transferring files,(SMTP): for transferring e-mail messages,(DNS): for translation of human-friendly domain names into IP addresses)
 - **Transport layer** - responsible for collecting the application layer message from the relevant end-point and transferring it to the network layer to be communicated over the network. The two important protocols used in the transport layer are:
    - Transmission Control Protocol (TCP): for reliable and connection-oriented data transfer
    - User Datagram Protocol (UDP): for fast, unreliable, and connection-less data transfer
- **Network layer** - responsible for transferring data from one system to another on the network. The main protocol used at the network layer to transfer data is Internet Protocol (IP). The data packet at the network layer is called a `datagram`.
- **Link layer** - responsible for communication between one device and its immediate neighbor(routers, switches, or other computers). The data packet at the link layer is called a `frame`.
- **Physical layer** - responsible for breaking the data frame into bits, converting it into a form that can be transmitted over the physical communication line, and transferring it.

### OSI Reference Model
Open System Interconnection - purpose is to show how to facilitate communication between different systems without requring changes in logic underlying software and hardware.

### Application architectures
- client-server
- peer to peer
  
- Server - the one who provides requested services
   - always-on host
   - permanent IP address
   - data centers for scaling

- Client - the ones who request services.
  - communicate with server
  - may be intermittently connected
  - may have dynamic IP addresses
  - do not communicate directly with each other 
 
 - P2P:
   - no always-on server
   - arbitrary end systems directly communicate
   - peers request service from other peers, provide service in return to other peers
   - self scalability – new peers bring new service capacity, as well as new service demands
   - peers are intermittently connected and change IP addresses
   - complex management
  
### Process Communication
Process: program running within a host

- within same host, two processes communicate using inter-process communication
- processes in different hosts communicate by exchanging messages

Process sends/receives messages to/from its **socket**.A socket is an endpoint of a two-way communication link between two processes running on a network. In simpler terms, a socket is like a telephone number or an address that enables two programs or processes to communicate with each other over a network.

## Web and HTTP
HTTP stands for Hypertext Transfer Protocol, and it is the foundation of data communication on the World Wide Web. It is a protocol that defines how messages are formatted and transmitted over the internet between web servers and web clients, such as web browsers. 

- **Non-persistent HTTP** - the older version of the protocol, where a new connection is established between the client and server for each HTTP request/response transaction.
  - RTT(Round trip time) - time for a small packet to travel from client to server and back
  
  Non-persistent HTTP issues:
- requires 2 RTTs per object
- OS overhead for eachTCP connection
- browsers often open parallel TCP connections to fetch referenced objects
  
- **Persistent HTTP** - a newer version of the HTTP protocol that allows for multiple requests and responses to be sent over a single connection
  - server leaves connection open after sending response
  - subsequent HTTP messages between same client/server sent over open connection
  - client sends requests as soon as it encounters a referenced object
  - as little as one RTT for all the referenced objects
