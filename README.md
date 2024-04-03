![image](https://github.com/DurgaV240106/4.Execution_of_NetworkCommends/assets/144870878/912e35d8-853b-4331-bf76-38a32d81eba9)# 4.Execution_of_NetworkCommands
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
CLIENT:

```import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())

```
```
SERVER:

```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())

```
TRACEROUTE COMMAND:
```
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```

## Output
PING COMMAND:

CLIENT:

![Screenshot 2024-04-03 141541](https://github.com/DurgaV240106/4.Execution_of_NetworkCommends/assets/144870878/02a8cbb7-b4fb-45fd-8dec-9b7065bb5989)

SERVER:

![Screenshot 2024-04-03 141618](https://github.com/DurgaV240106/4.Execution_of_NetworkCommends/assets/144870878/848acb97-28fd-4732-8857-95f531ddce59)

TRACEROUTE COMMAND:

![Screenshot 2024-04-03 141709](https://github.com/DurgaV240106/4.Execution_of_NetworkCommends/assets/144870878/1de7c023-4a23-4d48-a594-cdb8e6586e9d)


## Result
Thus Execution of Network commands Performed 
