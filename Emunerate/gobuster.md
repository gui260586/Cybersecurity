# DNS
```bash
gobuster dns -d [host] -w /usr/share/wordlists/seclists/Discovery/DNS/subdomains-top1million-5000.txt
```

# Rechercher les fichiers
```bash
gobuster dir -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -u [url] -x txt,html,php
```

Explication des arguments
  - -d => Url du site à attaquer pour le mode DNS
  - -u => Url du site à attaquer pour le mode recherche
  - -w => Utilisation d'une liste
  - -x => Chercher les fichiers avec les extensions (sans point et séparer par des virgules)
  - --exclude-length X => Ignore les réponses dont la taille est X
