# Computer Networks

# Solve ALL HOMEWORKS!!

* Communication of hosts is defined by computer networks
* Host are computers, servers, smartohones
* Host can be connected either directly via point to point link or indirectly through some networking devices
* Switch, Routers, Hubs are some of the networking devices

## Switching

* Before the invention of internet, telephone lines were used as primary source of communication
* Types of switching techniques
    1. Circuit Switching -> refer circuit_switching.png
        * A dedicated circuit establishment is done to connect one user to another
        * Switches completes the circuits and creates a path.
        * Inefficient utilization of network resources
        * Limited number of users can send their data
        * Expensive
    2. Packet Switching -> refer packet_switching.png
    * [Refer Here for packet switching](../Basics%20of%20%20CN/notes.md)
    1. Virtual Circuit Switching

## 2 Process Communication 

[Refer Here for 2 process communication](../Basics%20of%20%20CN/notes.md)

## TCP/IP Model

* Data Communication mode that works on packet switching/ store and forward network

```md
1. Application Layer
2. Transport Layer
3. Network Layer
4. Data Link Layer
5. Physical Layer
```

## OSI Model

```md
1. Application Layer
2. Presentation Layer
3. Session Layer
4. Transport Layer
5. Network Layer
6. Data Link Layer
7. Physical Layer
```

## Application Layer

[Refer Here for Application Layer](../Basics%20of%20%20CN/notes.md)

### Application Layer protocols

#### DNS

* Used to map between IP address' to 'Host Name' and vice versa

1. Distributed Database: Implemented in hierarchy of many name servers
2. Hosts (DNS clients) and DNS servers communicated to resolve names

* DNS Hierarchy
    1. Root Name Servers
    2. Top-level Domain Name Servers -> .in, .com, .org, etc
    3. Authoritative Name Server
### Application Layer protocols

#### DNS

* Used to map between IP address' to 'Host Name' and vice versa

1. Distributed Database: Implemented in hierarchy of many name servers
2. Hosts (DNS clients) and DNS servers communicated to resolve names

* DNS Hierarchy
    1. Root Name Servers
    2. Top-level Domain Name Servers -> .in, .com, .org, etc
    3. Authoritative Name Server

#### HTTP

* HTTP picks Web page objects from the server and gives it to the client.
* Follows Client - Server Model
* All web browsing is done using HTTP
* Stateless protocol

* Non Persistent HTTP/1.0
    * At most 1 object sent over the connection
    * Downloading multiple objects requires multiple connections

* Persistent HTTP/1.1
    * Multiple objects can be requested on the same TCP connection.

#### SMTP

* Mail transfer between client and server
* USes TCP to reliably transfer email message
* SMTP uses persistent TCP TCP connection
* Stateful protocol

#### FTP

* Reliable transfer of files
* USes 2 TCP connection for control and data
* It is a stateful protocol
* It can be used to transfer any kind of file  

#### DHCP

* Protocol For Dynamic IP address allocation

#### SNMP

* It is a network management protocol

#### HTTP

* HTTP picks Web page objects from the server and gives it to the client.
* Follows Client - Server Model
* All web browsing is done using HTTP
* Stateless protocol

* Non Persistent HTTP/1.0
    * At most 1 object sent over the connection
    * Downloading multiple objects requires multiple connections

* Persistent HTTP/1.1
    * Multiple objects can be requested on the same TCP connection.

#### SMTP

* Mail transfer between client and server
* USes TCP to reliably transfer email message
* SMTP uses persistent TCP TCP connection
* Stateful protocol

#### POP / IMAP

* POP -> Post office protocol
* IMAP -> Internet Mail Access Protocol

#### FTP

* Reliable transfer of files
* USes 2 TCP connection for control and data
* It is a stateful protocol
* It can be used to transfer any kind of file 

## Two Process Communication

[Refer Here for Application Layer](../Basics%20of%20%20CN/notes.md)

## Protocol Data Unit

[Refer Here for PDU](../Basics%20of%20%20CN/notes.md)

## Transport Layer Protocols

[Refer Here for Transport Layer Protocols](../Basics%20of%20%20CN/notes.md)

[Refer Here for Protocol Mapping](protocol_mapping.png)

## Network Layer

[Refer Here for Network Layer Protocols](../Basics%20of%20%20CN/notes.md)

## Routing

[Refer Here for Routing](../Basics%20of%20%20CN/notes.md)

## Data Link Layer

[Refer Here for Data Link Layer](../Basics%20of%20%20CN/notes.md)

## Physical Layer

[Refer Here for Physical Layer](../Basics%20of%20%20CN/notes.md)

## Network Delays

* There are 4 types of Network delays
    1. Transmission delay - major
    2. Propagation delay - major
    3. Queuing delay - minor
    4. Processing delay - minor
* There are a few assumptions in Network delays
    1. Negligible overhead in IP packet -> Ignore IP packet header size
    2. Negligible over head in Frame -> Ignore header and footer size

1. Transmission Delay
    * Time required to transmit a packet/frame over a link
    * Tx inversely proportional to Data Transfer rate
    * Tx is directly proportional to Frame size
    * Frame size 5k bits data transfer rate is 1k bps. Tx = 5 seconds
    * Tx = (Packet size)/(Data Transfer Rate)
    * Data Transfer rate is also called as bandwidth
    * Baud Rate -> Number of signals generated into channel per second
    * [Refer Packet Size](Computer%20Networks/computer_networks/packet_size.png)
    * if 1 bit is represented by 1 signal -> bit rate = Baud rate
    * If 1 bit is represented by 2 signals -> bit rate = Baud rate / 2 
    * [Refer Transfer Rates](Computer%20Networks/computer_networks/transfer_rates.png)

    ```md
    * packet size = 50KB, transfer rate = 100 Kbps
        * size = 50*8 * 2<sup>10</sup> b = 400 * 2<sup>10</sup> b
        * delay = 4 * 2<sup>10</sup> * 10<sup>-3</sup> sec = 4096 milliseconds
    ```

2. Propagation Delay
    * Time required for signal to travel from one end to other end of a link
    * Denoted by Tp
    * Tp is Directly proportional to Distance
    * Tp is inversely proportional to signal propagation speed
    * 4 KM wire, with 10^5 m/s speed, Tp = 4000/10^5 = 0.04 seconds = 40 milliseconds
    * Tp = Distance / Signal Speed if given in m/s
    * Tp = Distance / Signal Speed if given in seconds per meter
    * Round trip Tp = 2 * Tp
    
    ```md
    * 7KM wire, 20 millisecs per meter transfer rate
        * Tp = 7000 * 20 * 10<sup>-3</sup> = 140 seconds 
    ```

3. End to End delay
    * Time required for a packet to be transmitted from transmitter to the receiver
    * End to end delay is propagation delay + transmission delay

    * Case 1
      * If frame size is small transmission delay < propogation delay
    * Case 2
      * If frame size is large transmission delay = propogation delay
    * Case 3
      * Frame size is too large that tansmission delay > propogation delay
    * If there are wires of 2 materials half with delay tp1 and the rest with tp2. Then E2E delay = tx + (tp1 + tp2)

4. Store and Forward Delay

    * Layer 2 devices for Store and Forward -> Switch or bridge
    * Layer 3 device -> router
    * E2E delay = (tx + tp1) + {queue + processing + tx} + tp2
    * sfd = {queue + processing + tx}

## Questions

1. The PDU for Application layer in internet stack is
    * Message

2. 2 hosts A and B, bandwidth of link is 500 Kbps, tp = 150 ms. Host A sends 15,000 bytes to host B dividing file into 5000 bytes Calculate amount of time required in ms for the file completely from A to B

```md
total = 120,000 bits
speed = 500,000 bits/s

tx = 40000/500000 = 0.08s = 80ms

End to End delay = (N * tx) + tp

E2E = 3*80 + 150 = 390ms
```