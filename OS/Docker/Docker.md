# Liste des images 
```bash
docker image ls 
```

# Monter une image 
Montage d'une image dans /mnt et lancement de bash
```bash
docker run -v /:/mnt --rm -it [image] sh 
```

# Si docker pas dispo dans le container
Tenter de faire un fdisk –l et regarder celui qui est en "boot" et lancer : (exemple si "boot" est dans /dev/sda1)
```bash
mount /dev/sda1 /mnt  
```
