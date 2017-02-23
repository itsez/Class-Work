#!/usr/local/bin/python
from socket import *
from threading import Thread
'''
Author:John Hewitt

TCPServer.py is a TCP connection oriented server that takes a lowercase string
and converts it to upper case then sends it back to the client. This server 
can support up to 5 different clients (can be changed just didn't feel like it 
needed to at the moment) 
'''
def newClient():
    connectionSocket, addr = serverSocket.accept()  #establish connection  
    sentence = connectionSocket.recv(1024)          #recieve first input
    a = "quit"                                      #string to check
    while a != sentence.decode():
        capitalizedSentence = sentence.upper()      #converts sentence
        connectionSocket.send(capitalizedSentence)  #sends capital sentence to client
        sentence = connectionSocket.recv(1024)      #gets next input
    connectionSocket.close()                        #close the connection to client

serverPort = (removed for security)         #assigned port number
serverSocket = socket(AF_INET,SOCK_STREAM)  #associate server port number with socket
serverSocket.bind(('',serverPort))          #welcoming socket
serverSocket.listen(5)                      #listen for TCP connection requests ()-is max num of queued connections
print('The server is ready to receive')

for i in range(5):
    Thread(target=newClient).start()        #start a new thread for new client
serverSocket.close()                        #close server doesn't get called right now cause ctrl-C is a thing

