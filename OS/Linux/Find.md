# Rechercher dans les fichiers dans le dossier courant avec une REGEX 
```bash
egrep -Eo "[REGEX]" * 
```

# Rechercher dans les fichiers dans le dossier courant avec un mot 
```bash
grep -i [word] * 
```

# Rechercher des fichiers partout 
```bash
find / -type f -name [file]* 2> /dev/null 
```

# Rechercher du contenu dans les fichiers récursivement
```bash
grep -ri '[word]' 
```

# Rechercher les commandes pouvant être lancées en sudo
```bash
find / -perm -u=s -type f 2>/dev/null 
```

# Rechercher les fichiers par permissions en retirant les denied
```bash
find / -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null;  
```
