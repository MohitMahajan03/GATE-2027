# Computer Networks

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

```
Application Layer
Transport Layer
Network Layer
Data Link Layer
Physical Layer
```

## OSI Model

```
Application Layer
Presentation Layer
Session Layer
Transport Layer
Network Layer
Data Link Layer
Physical Layer
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

### Questions

1. The PDU for Application layer in internet stack is
    * Message