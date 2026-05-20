# 4.Execution_of_NetworkCommands
## NAME : NAVEEN M
## REGISTER NO: 212225230197
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>
## Program:
server:

```
import socket
from pythonping import ping
s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)
print("Server waiting...")
c, addr = s.accept()
print("Connected with:", addr)
while True:
    hostname = c.recv(1024).decode()

    if not hostname:
        break

    try:
        result = ping(hostname, verbose=False)
        c.send(str(result).encode())
        
    except Exception:
        c.send("Not Found".encode())
c.close()
s.close()
```
Client:
```
import socket
s = socket.socket()
s.connect(('localhost', 8000))
host = input("Enter hostname: ")
s.send(host.encode())
result = s.recv(1024).decode()
print("Result:")
print(result)
s.close()
```

## Output

<img width="1277" height="298" alt="image" src="https://github.com/user-attachments/assets/d9716a87-ccba-4479-b977-54cbd288317e" />


## Result
Thus Execution of Network commands Performed 
