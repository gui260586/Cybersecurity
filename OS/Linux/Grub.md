# Bypass de l'authentification pour un accès root
Lors de l'apparition de la fenêtre GRUB, il faut appuyer sur "e". <br/>
Il faut rechercher ensuite la ligne `linux` suivi de `/vmlinuz...` ou `/boot/vmlinuz...`. <br/>
Remplacer le `ro` (Read-only) par `rw` (Read-write) et ajouter à la fin `init=/bin/bash` pour un prompt en root.
