The ISO/OSI model is a reference model that explains how computers communicate with each other over a network. It was proposed by the ISO (International Organization for Standardization) in 1984. The OSI model consists of 7 layers. Each layer of the OSI model has its own functionalities. This layered approach was designed in such a way that changes to one layer do not require changes to other layers, making this model as an efficient approach.

## Layers of the OSI model

1. Physical Layer
2. Data-Link Layer
3. Network Layer
4. Transport Layer
5. Session Layer
6. Presentation Layer
7. Application Layer

The above seven layers are discussed below

![7Layers.webp](https://github.com/prakshitvjain/OSImodel/blob/main/7Layers.webp)

Every message from the client side flows through the seven layers to the Physical layer and flows through numerous networks and traverses all the seven layers all the way to the Application Layer. Numerous processes like segmentation, routing, fragmentation etc take place during this interval. Let us dive deep into what actually happens in each layer. 
### Physical Layer
The Physical Layer is the lowermost layer in the OSI model and defines the mechanical and electrical specifications of the model. It is responsible for the actual transmission of data over physical medium using devices such as Cables, Hubs, Modems etc. Here the data is transmitted as Bitstream (stream of bits) from one node to another in a network. 

This layer also controls the transmission rate through which the bits are transmitted. This transmission mode can be half-duplex (one-way communication) or full duplex (two-way communication) depending upon the requirements of the Organisation. It showcases the topology (how devices or nodes are arranged in a network) of the network.

![[Physical.png | 700]]
##### Security Measure
The devices at physical layer should be protected from unauthorized access to avoid tampering with devices that could lead to loss of information.

### Data-Link Layer
The Data-Link Layer is responsible for reliable transfer of frames from one node to another. It converts the physical layer's raw bitstream to Frames. The header is added to the frame. The header contains the source address, destination address and relevant information of the frame. Switches and Bridges are common devices at this layer.

![[Datalink.png | 700]]

The Data-Link Layer is divided into two sub-layers
##### Logical Link Control Layer
The Logical Link Control layer is responsible for receiving data from the Network layer, encapsulating the data into frames and passing it to the MAC Layer. On receiving end, the data is extracted from the frames and forwarded to the Network layer. This layer also provides Flow Control.
###### Flow Control
Flow Control refers to a technique where constant data rate is maintained on either sides during transmission. This helps to prevent data corruption or congestion, ensuring smooth transmission. This acts as a safety measure during varying speeds or high traffic.
##### Media Access Control Layer
The Media Access Control Layer acts as a bridge between the Logical Link Control Layer and the Physical Layer. It is used to transfer frames over a network. The MAC Layer is responsible for Access Control.
###### Access Control
The Media Access Control Layer decides who in the communication channel has control over the channel and gets to send the data to avoid collisions. This is helpful when a single communication channel is shared by multiple devices.

### Network Layer
The Network Layer is responsible for sending data between devices that are located on different networks. The data at Network layer is referred to as a packet. It determines the best path for packets to travel from the source to the destination and handles routing of packets, which involves selecting the shortest or most efficient route. It connects different networks and enables communication between devices on separate networks. Routers are devices used at Network Layer.

![[Network.png  | 700]]

The Network uses the IP (Internet Protocol) to perform the transmission of the packets. The Network Layer adds the Source and the Destination Addresses to the packets via Headers ensuring that the packet reaches to the correct receiver. 

Below are the fields of IP Header (32 bits):

- Version: Version of the IP protocol
- HLEN: Length of the Header
- Source Address: The IP address of the sender
- Destination Address: The IP address of the receiver
- Total Length: Combined length of Header + Data
- Identification: Unique Identification of packets, used for reassembly
- Time to live: Maximum time the packet can hop before being discarded, decremented with each hop and discarded at zero.
- Flags: Used to control fragmentation (whether the packet can be fragmented or not)
- Fragment Offset: specifies the position of fragment in the packet, if fragmented.
- Header Checksum: Used to verify the integrity of the packet.
##### Security Measure
Hardware Firewalls can be implemented to maximize the security of the systems. This firewall also helps to prevent DDoS attacks. These devices can act as a solid defense from malicious and unauthorized access.
###### Firewall
Firewall is basically a protective wall that analyzes and monitors the incoming traffic and requests. It filters out the illegitimate requests and allows only legitimate traffic to enter the network using appropriate guidelines set by the security team. The suspicious or illegitimate requests are discarded by the firewall protecting the system.

### Transport Layer
The transport layer ensures that data is transferred completely and in order which it was sent. The data in the transport layer is called Segments. It is responsible for the end-to-end delivery of the complete message. The transport layer also provides the acknowledgment of the successful data transmission and re-transmits the data if an error is found. Popular protocols used in Transport Layer are TCP and UDP.
##### Transmission Control Protocol
TCP is a reliable and connection-oriented protocol used to transfer segments where the data is reordered the way it was sent. If the segment does not reach the receiver i.e the sender does not receive acknowledgement, the segment is re-transmitted. It is comparatively slower than UDP.
##### User Datagram Protocol
UDP is a fast, unreliable and connection-less protocol used to transmit segments at a faster rate. Here speed is the priority and not the data itself and so, the sender does not wait for any acknowledgement. Highly used for Streaming purposes.

![[Transport.png | 700]]
##### Security Measure
 Protocols like SSL (Secure Socket Layer), TLS (Transport Layer Security) are to be used to securely handle the data in transit.
 The network traffic is to be continuously monitored to identify and detect any unusual or malicious activity.

### Session Layer
The Session Layer is responsible for establishing, maintaining and terminating the interactions between the devices. The Session Layer acts as a dialog controller by creating a dialog where devices can interact. The Session Layer also provides Synchronization.

![[Session.jpg]]
##### Synchronization
This layer allows to add checkpoints called synchronization points in the data. These synchronization points help to rollback data loss is avoided.
If some error occurs during transmission of data, then the transmission starts again from those checkpoints, preventing data loss.

### Presentation Layer
The Presentation Layer also known as Translation Layer, is mainly concerned with the syntax and semantics of the data that is being transmitted over the network.

![[Presentation.png]]

- It is used the extract data from application layer and manipulate the data in-accordance to supported formats.
- It is used for Encryption and Decryption of data using algorithms like AES (Advanced Encryption Standard), RSA etc.
- It is also used for compression of large files.

### Application Layer
The Application Layer is the uppermost layer of the OSI model, which produces the data that is to be transferred over the network and displays the received data to the user. This Layer provides multiple services such as email and file transfer. Protocols like FTP (File Transfer Protocol), SMTP (Simple Mail Transfer Protocol), DNS (Domain Name System) etc.

![[Application.png]]

A major application of Application Layer is File Transfer Access and Management(FTAM), which allows users to log on to a remote host and access, manage, retrieve and control files on that remote host. Protocols like Telnet, SSH (Secure Shell) etc.
##### Security Measure
Web Application Firewalls are to be implemented to ensure that malicious attacks like SQL injection and Cross Site Scripting (XSS) are handled by filtering the HTTP requests and responses.
