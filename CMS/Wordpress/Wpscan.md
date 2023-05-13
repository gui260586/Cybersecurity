# Scan et énumération User-Password 
```bash
wpscan --url http://test/ -e u -P /usr/share/wordlists/rockyou.txt  
```

Explication des arguments
  - -e => Enumération
    - u => ID des utilisateurs
  - -P => Liste de mot de passe à utiliser pour tenter une connexion
  - --url => Url ou IP du site à attaquer
