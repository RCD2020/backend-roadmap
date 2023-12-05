# How Does the Internet Work

> Notes on cs.fyi's 2023 article, [How does the Internet Work?](https://cs.fyi/guide/how-does-internet-work)

## Vocab

**Network**: Group of computers or other devices which are connected to each other.

**Packet**: Small unit of data transmitted over the internet.

**Router**: A device that directs packets of data between different networks.

**Internet Protocol (IP)**: Responsible for routing packets to their correct destination.

**IP Address**: A unique identifier assigned to each device on the network, used to route data to the correct destination.

**Transmission Control Protocol (TCP)**: Ensures packets are tranmitted reliably and in the correct order.

**Domain Name**: A human-readable name that is used to identify a website, such as google.com.

**DNS**: The Domain Name System is responsible for translating domain names into ip addresses.

**HTTP**: The HyperText Tranfer Protocol is used to tranfer data between a client (such as a web browser) and a server (such as a website).

**HTTPS**: An encrypted version of HTTP that is used to give secure communication between client and server.

**SSL/LTS**: The Secure Sockets Layer and Transport Layer Security protocols are used to provide secure communication over the internet.

## TCP/IP Vocab

**Ports**: Ports are used to identify the application or service running on a device. Each application or service is assigned a unique port number, allowing data to be sent to the correct destination.

**Sockets**: A socket is a combination of an IP address and a port number, representing a specific endpoint for communication. Sockets are used to establish connections between devices and transfer data between applications.

**Connections**: A connection is established between two sockets when two devices want to communication with each other. During the connection establishment process, the devices negotiate various parameters such as maximum segment size and window size, which determine how data will be transmitted over the connection.

**Data Transfer**: Once a connection is established, data can be transferred between the applications running on each device. Data is typically transmitted in segments, with each segment containing a sequence number and other metadata to ensure reliable delivery.

## SSL/TLS Vocab

**Certificates**: SSL/TLS Certificates are used to establish trust between the client and server. They contain information about the identity of the server and are signed by a trusted third party (a Certificate Authority) to verify their authenticity.

**Handshake**: During the SSL/TLS handshake process, he client and server exchange information to negotiate the encryption algorithm and other parameters for the secure connection.

**Encryption**: Once the secure connection is established, data is encrypted using the agreed-upon algorithm and can be transmitted securely between the client and server.

## Emerging Technologies

**5G**: 5G is the latest generation of mobile network technology, offering faster speeds, lower latency, and greater capacity than previous generations. It is expected to enable new use cases and applications, such as autonomous vehicles and remote surgery.

**Internet of Things (IoT)**: IoT refers to the network of physical devices, vehicles, home appliances, and other objects that are connected to the internet and can exchange data. As IoT continues to grow, it is expected to revolutionalize industries such as healthcare, transportation, and manufacturing.

**Artificial Intelligence (AI)**: AI Technologies such as machine learning and natural language processing are already being used to power a wide range of applications and services, from voice assistants to fraud detection. As AI continues to advance, it is expected to enable new use cases and transform industries such as healthcare, finance, and education.

**Blockchain**: Blockchain is a distributed ledger technology that enables secure, decentralized transactions. It is being used to power a wide range of applications, from cryptocurrency to supply chain management.

**Edge Computing**: Edge computing refers to the process of storage and processing of data at the edge of the network, rather than in centralized data centers. It is expected to enable new use cases and applications, such as real-time analytics and low-latency applications.

## 3 Parts of the Internet
> Notes on vox.com's 2015 article by Timothy B. Lee, [The internet, explained](https://www.vox.com/2014/6/16/18076282/the-internet)

**The Last Mile**:
The Last Mile is the largest part of internet infrastructure, and it refers to all the physical infrastructure that connects the users/devices to the web. This includes all the cables that connect homes and towers that connect cellular devices.

**Data Centers**:
Rooms full of servers that store data and host online apps and content.

**The Backbone**:
The long distance network - mainly fiber optic cable - that carry data between data centers and the last mile.


# How Does the Internet Work?
> Notes on Stanford's 2002 article by Rus Shuler, [How Does the Internet Work?](https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm)

When connecting to the internet through your ISP, you are given a temporary IP Address for the duration of your dial-in session. If you connect through Local Area Network (LAN), then you might have a permanent IP Address or it might obtain a temporary one through a Dynamic Host Configuration Protocol (DHCP). But in any case, your IP Address will be unique.

**Ping**: If you are using Windows or a Unix based operating system (including MacOS) you can `ping` sites from your terminal, and it will tell you how long it took to get a response as well as if you used a Domain Name, it will tell you the IP Address you connected to. Hit **Ctrl+C** to interrupt this operation.

**TCP/IP Stack**: The TCP/IP Stack is what allows us to send information over the internet, but it does so in the following layers:

Protocol Layer                       | Description
------------------------------------ | -----------
Application Protocols Layer          | Protocols specific to applications such as WWW, e-mail, FTP, etc.
Transmissions Control Protocol Layer | TCP directs packets to a specific application on a computer using a port number
Internet Protocol Layer              | IP directs packets to a specific computer using an IP Address
Hardware Layer                       | Converts binary packet data to network signals and back (E.g. ethernet network card, modem for phone lines, etc.)

**Trace Route**: You can trace the route your packets travel by running `traceroute {Domain Name or IP}` (`tracert` on Windows) and it will print out all the routes that exchanged your packet.

**Network Service Provider (NSP)**: An NSP is large network that connects other networks together to direct packet traffic. Each one is required to connect to atleast 3 **Network Access Points (NAP)** or **Metropolitan Area Exchanges (MAE)**. An MAE is just a NAP but privately owned. NAPs and MAEs are referred to generally as **Internet Exchange Points (IX)**.

**Routing Tables**: How does a computer find another IP Address? First the computer sends the packet to the router it is connected to. The router then checks its Routing Table, which is a collection of all the IP Addresses it is assigned to keep track of. If it does not contain the target IP, then it sends the pack along its default path to another router, where the same steps are repeated until the default path eventually leads to an NSP, which contains huge routing tables. Once the correct IP is found, then it starts routing down the chain.

**Simple Mail Transfer Protocol**: Protocol for emails