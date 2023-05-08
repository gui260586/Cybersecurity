# Lister les sous-domaines
```bash
fuzz -c -f subdomains.txt -w /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt -u [url] -H "Host: FUZZ.[url]" --hl 107
```

Explication des arguments
  - -c => Sortie avec coloration syntaxique
  - -f => Sortie dans un fichier
  - -H => En-tête à utiliser
  - -u => Url du site à attaquer
  - -w => Utilisation d'une liste
  - --hl => Cacher les réponses avec X lignes (107 dans l'exemple)
