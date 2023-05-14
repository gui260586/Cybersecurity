# Décrypter avec private.key 
```bash
openssl rsault -decrypt -inkey private.key -in [fileEncrypted] -out plaintext.txt
```

# Décrypter avec le password et le fichier encodé
Si on connait l'algorithme et le nom d'itération
```bash
openssl aes-256-cbc -d -iter 10 -pass pass:$(cat /pass.txt) -in flag.enc -out flag.dec
```

# Décrypter avec gpg 
```bash
gpg -f [file.gpg]
```

# Sites de décodage d'algorithme
  - [Boxentriq](https://www.boxentriq.com/)
  - [Dcode](https://www.dcode.fr/)
