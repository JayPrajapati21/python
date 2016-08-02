#PYTHON
#Simple Server using Python

        #for starting server:
        import socket
        tcpsocket=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
        tcpsocket.setsockopt(socket.SOL_SOCKET,socket.SO_REUSEADDR,1)
        tcpsocket.bind(("0.0.0.0",8000))
        tcpsocket.listen(1)
        print "Waiting For Client...."
        (client,(ip,port))= tcpsocket.accept()
        print "Received connection from " , ip
        print "Starting ECHO output..."
        data='dummy'
        while len(data):
	       data=client.recv(2024)
	       print "Client sent ",data
	       client.send(data)
       print "Closing Connnection"
       client.close()
       tcpsocket.close()
#To Connect to server....
  we can use netcat tool...
  let us try to connect, to this network....
  @nc 127.0.0.1 8000
  syntax : nc [hostname] [port(s)]
