# Client Server Architecture:
Sometimes an application's structure takes on a client server nature. A server application provides services such as access to a database ,serving network time, authentication and access to shared resources or serving out chat conversations. Client application are then created which make use of these services. To initiate a point to point client server connection, the TCP is used. TCP is a reliable protocol - in other words, it gurantees the delivery of the data it transmits in the form of the packets.If packets are lost or damaged, TCP will resend the data until it verifies that packets have been successfully transmitted.TCP is needed for appliocations that must reliably send messages back and forth or initiate file transfers to ensure that a perfect copy of data arrives at other side uncorrupted.
# TCP/IP Sockets:
When establishing connectivity, client and server each bind a socket to their end of the connection. Once a connection has been
established the client and server both read from and write to the socket when communicating. A socket is a combination of both an IP address and a port number. Each socket used in client server communication is an endpoint of the two way communictaion link used to send packets between applications. Multiple TCP connections can be initiated between each client and a server and each connection is unique by its combination of ports aand endpoints.The server runs on a specific host where it creates and continuously listens to a "server socket" that is bound to a specific port number and waits for clients to make connection requests. The client must know correct port and the ip address or host name of server to initiate a connection request and identify itself. When server accepts the client's connection request,
the client also creates a socket and communication between client and server takes place as both read from and write to their sockets.
Java uses the Socket and ServerSocket classes from the java.net package to implement client-server communication.  
In the server application, once a ServerSocket has been instantiated with a designated port, a new Socket is created to accept the 
ServerSocket's connection request by calling the accept() method on the ServerSocket object. Then InputStreamReader, Bufferedreader and 
PrintStream class objects are instantiated. The BufferedReader object's readLine() method is used to retrieve input from the client and 
the PrintStream object's println() method is used to send output to the client. 
In the client application, a new Socket is created if the server's ServerSocket accepts the connection request. The connection is 
requested by instantiating a Socket class object and passing in the server's IP address or host name and the selected port as 
arguments. The InputStreamReader, BufferedReader and PrintStream class objects are instantiated. The BufferedReader object's 
readLine() method is used to retrieve input from the server and PrintStream object's println() method is used to send output to the 
server.
# Process regarding Client Server Apllications:
1 Create a Socket or ServerSocket object and open it over a specified port and IP address or host name.
2 Instantiate InputStreamReader, BufferedReader and PrintStream objects to stream data to and from each socket.
3 Read from and write to the stream between the sockets using their agreed upon protocol.
4 Close the input and output streams.
5 Close the Socket or ServerSocket objects.

