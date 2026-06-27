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

### Application Layer

* Network application program is program that connects the User to the application layer. EX: Browsers
* Port number is a 16 bit identifier that is used to identify a network process in a machine. It is machine dependent
* Application layer protocols
    * DNS: Domain Name System
    * HTTP: Hyper Text Transfer Protocol
    * FTP: File Transfer Protocol
    * SMTP: Simple Mail Transfer Protocol
    * HTTPS: Secure HTTP

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

### Network Layer

* It provides host-to-host (Inter-networks: Source and Destination hosts belong to different networks) communication services
* It is responsible for forwarding and Routing
* It uses the IP protocol (Internet Protocol)

### Data Link Layer

* Responsible for Node-to-Node (hot-to-hop) communication (Intra-network: Source and Destination hosts belong to same network)

* Node is a host or a Router

### Physical Layer

* Responsible for transmission of Data in form of bits
* Uses Copper cable, fibre cable and wireless mediums
* Performs Encoding and Decoding

### Protocol Data Unit

* It is the basic unit of exchange
* This unit is decided Between same protocol of different machines
* Refer pdu_mappings.png

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

### Protocol

* In Networking it is a set of rules defined on how data is exchanged

### Misc

* Ping is a utility to check connection between client - server, server - server, client - client