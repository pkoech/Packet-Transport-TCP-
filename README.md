# Transport TCP

**Introduction**

The goal of this project is to implement a Socket that implements a TCP protocol similar to those you can find in the Internet. A socket is an abstraction between the application layer and the transport layer that allows an application to easily use the underlying transport protocol (TCP in this case). While sockets are usually implemented by the operating system, your socket will be a user space implementation written in Python. A network simulator and a Python TCP/IP stack is provided. In this project, application is implemented with Socket. I implemented the core parts of the protocol, and the tests is provided will act as applications. 

**Background**

   **Sockets**

  Sockets abstract away establishing a connection, and sending and receiving data. Further, a TCP socket provides reliable, ordered, and error-checked delivery of a stream of bytes. Usually, each connection is composed of two sockets: the local socket, and the remote socket. 

  For example, the local socket might be created and utilized by your web browser, and the remote socket could be created and managed by a web server. In typical usage, one socket actively connects (this would be your web browser), and the other passively connects (this would be the web server). In a typical scenario, the server creates a socket and then calls bind and listen functions to create a socket waiting for a connection. 

  Clients can establish TCP connections to the server by calling connect, which the server can accept. Underlying this sequence of function calls is the TCP 3-way handshake. Once the connection is established, either side can send data with send and the other side can receive data with recv.

  **TCP**

  TCP (Transmission Control Protocol) is a Layer 4 protocol that provides a byte stream abstraction. The stream of bytes are broken into packets (or segments in TCP lingo) and delivers those packets. It provides multiplexing and demultiplexing, reliability, connection orientated communication, and flow and congestion control.

  A connection can progress through a series of states during its lifetime. The possible states are listed in the diagram below. For this project you only need to implement a subset of TCP for the client and not the server. You will not have to implement the LISTEN or SYN RECEIVED state transitions, and you’ll be given a large fraction of the rest of state transitions. The entire state transition diagram is detailed below for reference. Further, the TCP stack you will implement will only support the ACK, SYN and FIN control


