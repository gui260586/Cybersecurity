# Utilisation
```bash
volatility -f file.dmp <plugins>
```

Pour la liste des plugins
```bash
volatility -h 
```

Exemple de plugins :
  - hashdump : Extraction des hashes NTLM des users du dump
  - imageinfo : Information sur le type de profile (Windows, Linux, etc...)
