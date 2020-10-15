# python-server
#using python to built server
###########################

import os
from socket import *
nm=gethostname()
ip=gethostbyname(nm)
print("the machine ip is ...:",ip)
port=8888
bsize=1244
s=socket(AF_INET,SOCK_STREAM)
###########################
s.bind((ip,port))
s.listen(1)
###########################
os.system("clear")
print("welcome". center(50))

while True:
	client,add=s.accept()
	re=client.recv(bsize).decode()
	print(re)
	m=input("<server':write messag.:").encode()
	client.send(m)
	client.close()

