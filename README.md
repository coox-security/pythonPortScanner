# pythonPortScanner
Simple scanner to run check for common open ports.


import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server = 'google.com'

# trys to connect, returns true if allowed, false if not
def pscan(port):
	try:
		s.connect((server,port))
		return True
	except:
		return False

# for loop to cycle through ports and print results
for x in range(1,1024):
	if pscan(x):
		print('Port',x,'is open')
		
	else:
		print ('Port',x,'is not open')
