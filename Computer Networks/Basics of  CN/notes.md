# Computer Networks Fundamental

## OSI and TCP/IP model

### OSI Model

* Open System Interconnection -> It is an ISO standard model
* It is a Conceptual Model
* It has a Seven layer architecture -> Refer OSI-model.png
* Where each layer is a group of functions based on similarity 
    ```
    7. Application
    6. Presentation
    5. Session
    4. Transport
    3. Network
    2. Data Link
    1. Physical
    ```
* Networking software is a part of OS

### TCP/IP model

* It combines the Top 3 layers of OSI model into 1 single layer -> Application Layer
* It has 5 layers
    ```
    5. Application Layer
    4. Transport Layer
    3. Network Layer
    2. Data Link Layer
    1. Physical Layer
    ```

### 2 Process Communication

* In Networking, 2 processes communicate with each other belonging to different hosts
* Communication over network by exchanging messages
* Process are uniquely identified by IP Address (32 bit) and Port Number (16 bit)
* Communication credentials used are Source IP address and Port number and Destination IP Address and Port number

1. Client - Server Model
    * Web browsing, Email
    * Whoever initiates connection is the client, the connecting process is the Server

2. Peer to Peer
    * Client to Client connection
    * Ex: Voice calling, Voice over internet protocol


### Application Layer

* Network application program is program that connects the User to the application layer. EX: Browsers
* Port number is a 16 bit identifier that is used to identify a network process in a machine. It is machine dependent
* Application layer protocols
    * DNS: Domain Name System
    * HTTP: Hyper Text Transfer Protocol
    * FTP: File Transfer Protocol
    * SMTP: Simple Mail Transfer Protocol
    * HTTPS: Secure HTTP

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

### Presentation layer

* Performs Code Conversion
    * Convert data into network standard code, before transmission. ASCII, EBCDIC, UNICODE
* Encryption and Decryption
* Compression and Decompression

### Session layer

* Session Establishment
* Dialog Management
* Authentication
* Authorizations

### Transport layer

* Provides logical communication between application process (processes running on different machine)
* Responsible for process to process (end to end) communication
* Performs multiplexing and demultiplexing
* Transport Layer Protocols
    * UDP: User Datagram Protocol
        * Minimal and required services
        * Unreliable Protocol
        * Provides fast communication
        * Connectionless
    * TCP: Transmission Control Protocol
        * Reliable
        * Slow
        * Connection oriented.

    * Refer -> protocol_mappings.png
* It takes messages from Application layer and breaks if they are big into smaller segments, and then adds it's header to the segments.

### Transport Layer Protocols

#### UDP

* User Datagram Protocol is a Connection less and unreliable service
* It is simple and fast
* Preferred for shorter communication - Query and Response

#### TCP

* Transmission Control Protocol provides Connection-oriented and reliable services
* Provides Flow, Error and COngestion Control
* Has connection establishment procedure, then proceeds for data transfer
* The connection is a logical connection
* Preferred 

### IP Allocation

* IP allocation happens when host connects to a network
* Unique IP address is assigned to it

1. Static Allocation -> Manual update
    * Need to manually change IP address when switching networks
2. Dynamic Allocation -> DHCP (Dynamic Host Configuration Protocol)

#### Network Address Translation

* A device That converts private IP address to public IP address and vice versa in Source IP address field while moving packet out of private network and into the private network

#### Routing

* Identifying best path between Source and Destination

1. Static Routing -> Non adaptive Routing
    * Uses Dijkstra's, Bellman-Ford, Floyd-Warshall Algorithms
    1. Shortest Path Algorithm
    2. Flooding
2. Dynamic Routing
    * Adaptive Routing
    1. Link state routing -> Uses Dijkstra
    2. Distance Vector Routing -> Uses Bellman Ford

#### Routing Protocols

1. Interior Gateway Protocol
    * Routing Information protocol -> Uses Distance Vector Routing
    * Open Shortest Path First (OSPF) -> Uses Link state Routing

2. Exterior Gateway Protocol
    * Border Gateway protocol -> Path vector Routing

#### Switching

* Process of forwarding packets towards destination

1. Circuit Switching
    * Establish dedicated path between sender and receiver
    * Connection oriented and reliable service
    * Example: Telephone Network
    * Inefficient and Costly
2. Packet Switching
    * Message divided into packets
    * No path reservation is required
    * Connection less and unreliable services
    * Example: Internet
    * Efficient utilization
3. Message Switching
    * No dedicated path
    * Store and Forward
    * Entire message is transmitted as single chunk

* Types of services

1. Connection Oriented Services
2. Connection Less Services

### Network Layer

* It provides host-to-host (Inter-networks: Source and Destination hosts belong to different networks) communication services
* It is responsible for forwarding and Routing
* It uses the IP protocol (Internet Protocol)
* So, the Segment of the Transport layer, is passed on to the network layer
* The network layer, if the Segment is large, breaks it into different datagrams and adds it's header to all datagram packets
* IP has 2 version 4 and 6
* IP v4
    1. Variable size header 20 bytes to 60 bytes
    2. TTL 8 bit [Used to prevent indefinite traversing of the packet]
    3. 32-bit IP address
    4. Contains Classfull and Classless IP Address
    5. IP address for v4 encountered Range problem
    6. Solution to the Range problem -> Network Address Translation (NAT)

* IP v6
    1. Fixed size 40 bytes
    2. Hop limit -> same as TTL 
    3. 128-bit size IP address
    4. Completely Classless IP address

* IP address
    * It is a unique idetifier
    * Assigned to a device that uses IP for communication
    * It is a Logical Address (IP address).
    * IP address -> NetID|HostID

* IP v4 address
    * Size of IPv4 address = 32 bits
    * Binary representation is done in 32 bits format
    * Dotted decimal representation -> 4 octet separated by .
    * P.Q.R.S -> 122.234.123.255
    * Range of every octet -> 0 to 255
    * Classfull IP v4
        * Refer -> classfull.png
        * Static Assignment
        * NetID bits are implicitly defined
        ```
        Class A:
            ->Address Starts with 0 bit
            ->Network ID 8 bits; Host ID 24 bits 
            ->Range: 0.0.0.0 to 127.255.255.255 
            ->Number of networks = 2<sup>7</sup> 
            ->Number of Hosts per network = 2<sup>24</sup>-2 
            ->Network mask = 255.0.0.0
        Class B
            ->Address Starts with 10 bits
            ->Network ID 16 bits; Host ID 16 bits 
            ->Range: 128.0.0.0 to 191.255.255.255 
            ->Number of networks = 2<sup>14</sup> 
            ->Number of Hosts per network = 2<sup>16</sup>-2 
            ->Network mask = 255.255.0.0 
        Class C
            ->Address Starts with 110 bits
            ->Network ID 24 bits; Host ID 8 bits 
            ->Range: 192.0.0.0 to 223.255.255.255 
            ->Number of networks = 2<sup>21</sup> 
            ->Number of Hosts per network = 2<sup>8</sup>-2 
            ->Network mask = 255.255.255.0 
        Class D
            ->Address Starts with 1110 bits
            ->Used for Multicasting 
            ->Range: 224.0.0.0 to 239.255.255.255
            ->Class D IPv4 address cannot be a host IP address
            ->It is used as "Group Id" by IGMP
        Class E
            ->Address Starts with 1111 bits
            ->Network ID 16 bits; Host ID 16 bits 
            ->Range: 240.0.0.0 to 255.255.255.255 
        ```
    * Classless IP v4 address
        * Dynamic Assignment
        * NetId bits need to be defined explicitly, They are assigned Dynamically
        * No Prefix bits for IP address
        * IP address in the form of P.Q.R.S/x
        * x represents number of network id bits

* IP v6 address
    * Binary representation of 128 bits each
    * Hexadecimal representation -> 8 hextet separated by colon
    * P:Q:R:S:T:U:V:W -> 2A01:0000:130F:0000:0000:09C0:876A:130B

* MAC Address
    * It is a physical device address
    * 48-bit size NIC Card address

* Modes of IP transmission
    1. Unicast -> 1 sender sends data to only 1 receiver -> one to one
        * Source IP -> Host IP address
        * Destination IP -> Host IP address
    2. Broadcast -> 1 sender sends data to all hosts in a network -> One to all
        * Source IP -> Host IP address
        * Destination IP -> Broadcast IP address -> 255.255.255.255
    3. Multicast -> 1 sender sends data to a group of hosts in a network -> one to many
        * Source IP -> Host IP Address
        * Destination IP -> Multicast Address [special IP address as a Goupe ID] -> IGMP -> Internet Group Message Protocol

### Data Link Layer

* Responsible for Node-to-Node (hot-to-hop) communication (Intra-network: Source and Destination hosts belong to same network)

* Node is a host or a Router
* Takes Datagram packet from Network layer, it adds Header and Footer and converts these packets into frames
* Line Configuration -> Attachment of Communication devices to a link
    1. Point to Point -> Dedicated link between sender and receiver
    2. Multipoint -> More than 2 devices sharing a single link, used for broadcast medium. EX: Bus Topology

* Services
    1. Framing
    2. Error Control
    3. Flow Control
    4. Access Control

#### Error Control

* Error : Corrupted Data

* Types:
    1. Single bit error
    2. Burst error

* Error Control -> Based on parity and extra bits
    1. Error detection: Can only detect errors, cannot correct, retransmission of corrupted data.
        * Cyclic redundancy check : Single bit parity
        * Checksum
    2. Error Detection and Correction: Forward error correction; Correct error and then forward
        1. 2D Parity
        2. Hamming Code

#### Flow Control

* Synchronization between transmitter and receiver to control the flow

1. Stop and Wait
2. Sliding Window
    1. Go Back N ARQ
    2. Selectiver Repeat ARQ (Automatic Repeat Request)

#### Network Topology

* Line Configuration -> attachment of communication devices to a link
    1. point to point -> Dedicated link between 2 devices
    2. Multipoint (Multidrop) -> More than 2 devices attached to single link, Usually a broadcast medium. Ex Bus topology.

* Transmission Mode -> Define the direction of signal flow between 2 linked devices
    1. Simplex Mode -> one way communication
    2. Half Duplex -> Either side communication at a time
    3. Full Duplex mode -> Both side communication is possible at same time

* Network Topology -> Arrangement of hosts inside a network
    1. Mesh -> Every device has dedicated point to point link with every other device
        * Total nodes = n
        * Total links = <sup>n</sup>C<sub>2</sub>
        * Advantages -> Fast and parallel Communication
        * Disadvantages -> High cost, insufficient utilization of links, (n-1) IO port per device
    2. Star -> Every device has dedicated point to point link, only to a central control, which can be hub, switch or router
        * Total nodes = n
        * Total links = n
        * Advantages -> easy insertion and removal of devices, easy to extend topology.
        * Disadvantage -> if central controller fails, then all communications stop
    3. Bus -> Every host connected to centralized backbone media/coaxial cable
        * Total nodes = n
        * Total links = 1
        * Multipoint configuration using access control method to control access to the bus at a time. Defined by MAC layer Protocol
        * Advantages -> Very low installation cost, preferable for long area network
        * Disadvantages -> If backbone media goes down.
    4. Ring -> Every host is connected to 2 adjacent host using point to point link in cyclic fashin
        * Total nodes = n
        * Total links = n
        * Simplex Communication using Access Control Method

#### Media Access Control

* It is the lower sub layer of Data Link Layer
* This layer determines who can have access to media on the multipoint line configuration.
* It is not useful in point to point line configuration
* Has multiple access protocols
* MAC Address
    * Used in identification of Source and Destination nodes of a packet
    * It is a physical address given on NIC card
    * MAC Address is of 6 bytes
    * MAC should be unique for all devices within the network
    * Hexa representation of MAC address - ac:d1:b8:d5:59:0d

### MAC Protocols

* MAC protocols are of 3 types
    1. Channel partitioning : Static allocation
    2. Random Access : No any allocation
    3. Taking Turns : Dynamic allocation

#### Channel Partitioning

1. TDMA : Time division Multiple access
2. FDMA: Frequency division Multiple access
3. CDMA : Code Division Multiple access

#### Random Access

1. ALOHA : Pure ALOHA and Slotted ALOHA

2. CSMA : Consists of CSMA/CA and CSMA/CD

#### Controlled Access MAC protocol

1. Reservation
2. Polling
3. Token passing

### Physical Layer
 
* Responsible for transmission of Data in form of bits
* Uses Copper cable, fibre cable and wireless mediums
* Performs Encoding and Decoding

### Protocol Data Unit

* It is the basic unit of exchange
* This unit is decided Between same protocol of different machines
* Refer pdu_mappings_2.png

### Service Data Unit

* Servicec Data Unit is the PDU of the Upper layer. For example Message from the Application layer is the SDU of Transport Layer

### Protocol

* In Networking it is a set of rules defined on how data is exchanged

### Networking Devices

* Refer -> network-devices.png
* Store Process and Forward devices
   1. Data Link Layer -> Switch (Bridge) : Performs MAC level forwarding
   2. Network Layer -> Router : Performs Routing from 1 network to another
   3. Application Layer -> Gateway : Also performs Routing; It is also called as protocol converter as it can convert format of packets
1. Physical layer -> Repeater and Hub
### Misc

* Ping is a utility to check connection between client - server, server - server, client - client