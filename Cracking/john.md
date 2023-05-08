# Crack d'un fichier shadow
```bash
john --format=sha512crypt shadow-file --wordlist=/usr/share/wordlists/rockyou.txt
```

# Crack d'un id_rsa
```bash
ssh2john id_rsa > hash
john hash --wordlist=/usr/share/wordlists/rockyou.txt
```

# Crack d'un MD5
```bash
john –-format=md5crypt hash --wordlist=/usr/share/wordlists/rockyou.txt
```

# Crack d'un zip
```bash
zip2john file.zip > hash
john hash --wordlist=/usr/share/wordlists/rockyou.txt
```

# Créer une liste de règles custom
Créer ou éditer le fichier `/usr/share/john/john-local.conf` <br/>
Exemple :
```
[List.Rules:WordLowerCaseHyphenUnderscoreYear]
l Az"[\-_]19[0-9][0-9]" <+
l Az"[\-_]20[012][0-9]" <+

[List.Rules:WordLowerCaseEnvHyphenUnderscoreYear]
l Az"-dev" Az"[\-_]19[0-9][0-9]" <+
l Az"-dev" Az"[\-_]20[012][0-9]" <+
l Az"[\-_]19[0-9][0-9]" Az"-dev" <+
l Az"[\-_]20[012][0-9]" Az"-dev" <+
l A0"dev-" Az"[\-_]19[0-9][0-9]" <+
l A0"dev-" Az"[\-_]20[012][0-9]" <+

[List.Rules:WordLowerCaseWithSuffix]
l Az"-dev" <+

[List.Rules:WordLowerCaseWithPrefix]
l A0"dev-" <+

[List.Rules:Guigui]
.include [List.Rules:WordLowerCaseWithSuffix]
.include [List.Rules:WordLowerCaseWithPrefix]
.include [List.Rules:WordLowerCaseHyphenUnderscoreYear]
.include [List.Rules:WordLowerCaseEnvHyphenUnderscoreYear]
```
Lancer la commande ci-dessous pour générer le fichier par rapport à une liste
```bash
john --rules=Guigui --wordlist=test.lst --stdout > out.txt 
```
