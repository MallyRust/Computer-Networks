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

### Delays
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
