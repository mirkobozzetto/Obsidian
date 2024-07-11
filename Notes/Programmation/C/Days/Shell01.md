
Chapitre IV : Exercice 01 : print_groups
---
Alors, pour le premier coup, faut que tu tapes cette commande dans ton shell :
```shell
#!/bin/sh
groups $FT_USER | tr ' ' ','
```
Comme ça, ça va afficher les groupes auxquels appartient ton user. Par exemple, si ton FT_USER c'est "toto", t'auras un truc du genre "toto,staff,admin"... 

Chapitre V : Exercice 02 : find_sh
---
Pour ce coup, faut que tu tapes ça dans ton shell :
```shell
#!/bin/sh
find . -name "*.sh" -exec basename {} .sh \;
```
Ça, ça va te sortir tous les fichiers qui finissent par ".sh", sans le ".sh". Genre, si t'as un fichier qui s'appelle "script.sh", ça va juste te sortir "script".

Chapitre VI : Exercice 03 : count_files
---
Pour celui-là, tu tapes ça :
```shell
#!/bin/sh
find . -type f -o -type d | wc -l
```
Ça, ça va te sortir le nombre de fichiers et de dossiers dans ton répertoire. Genre si t'as 10 fichiers et 5 dossiers, ça va te sortir 15.

Chapitre VII : Exercice 04 : MAC
---
Pour celui-là, tu tapes ça :
```shell
#!/bin/sh
ifconfig -a | grep -o -E '([[:xdigit:]]{1,2}:){5}[[:xdigit:]]{1,2}'
```
Ça, ça va te sortir toutes les adresses MAC de ta machine. Genre, ça peut te sortir un truc du genre "00:0c:29:63:92:c8".

Chapitre VIII : Exercice 05 : Can you create it ?
---
Pour celui-là, tu tapes ça :
```shell
#!/bin/sh
echo "42" > "\\?$*'MaRViN'*$?\\"
```
Ça, ça va créer un fichier qui s'appelle "\\?$*'MaRViN'*$?\\", et à l'intérieur, y aura juste le nombre "42". 

Chapitre IX : Exercice 06 : Skip
---
Pour celui-là, tu tapes ça :
```shell
#!/bin/sh
ls -l | awk 'NR%2'
```
Ça, ça va te sortir un "ls -l", mais une ligne sur deux, à partir de la première.

Chapitre X : Exercice 07 : r_dwssap
---
Pour celui-là, je te laisse faire, mais ça ressemble à un truc du genre :
```shell
#!/bin/sh
cat /etc/passwd | sed -n 'n;p' | cut -d : -f 1 | rev | sort -r | awk 'NR>=FT_LINE1 && NR<=FT_LINE2' | paste -sd, - | sed 's/$/./'
```
Faut que tu joues avec les variables FT_LINE1 et FT_LINE2 pour définir quelles lignes tu veux.

Chapitre XI : Exercice 08 : add_chelou
---
Pour celui

Chapitre XI : Exercice 08 : add_chelou
---
Là, c'est un peu chaud mais t'inquiète, on va le faire ensemble. Alors déjà, faut que tu saches que chaque caractère dans FT_NBR1 et FT_NBR2 représente un chiffre en base différente. Donc, faut convertir ces caractères en chiffres, les additionner, puis convertir le résultat en base "gtaio luSnemf". Ça ressemble à un truc du genre :
```shell
#!/bin/sh
echo $FT_NBR1 + $FT_NBR2 | tr "\'\"\?\!\\" "01234" | tr "mrdoc" "01234" | xargs echo "ibase=5; obase=23;" | bc | tr "0123456789ABC" "gtaio luSnemf"
```
Si t'as FT_NBR1='\"\"!\"\"!\"\"!\"\"!\"\"!\"' et FT_NBR2=dcrcmcmooododmrrrmorcmcrmomo, le résultat sera "Segmentation fault".

Voilà frérot, j'espère que ça t'aide ! 🤘 Si t'as d'autres questions, hésite pas à me demander, je suis là pour ça.