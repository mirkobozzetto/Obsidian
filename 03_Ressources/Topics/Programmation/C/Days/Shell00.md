
**Exercice 00 : Z**

Dans cet exercice, tu devais créer un fichier appelé "z" qui affiche simplement la lettre "Z" suivie d'un retour à la ligne. C'est très simple avec la commande `echo` :

```zsh
echo "Z" > z
```

**Exercice 01 : testShell00**

Cet exercice te demandait de changer les permissions d'un fichier. En utilisant la commande `chmod`, tu peux modifier les permissions. Par exemple, pour donner à "user" la lecture seule, "group" la lecture et l'exécution, et "other" l'exécution seulement, tu peux utiliser:

```bash
chmod 754 testShell00
```

**Exercice 02 : Owi, encore...**

Ici, tu devais créer plusieurs fichiers et répertoires avec des permissions spécifiques. Pour cela, tu peux utiliser les commandes `mkdir` pour créer des répertoires et `touch` pour créer des fichiers. Ensuite, tu peux modifier les permissions avec `chmod` comme dans l'exercice précédent.

**Exercice 03 : Connecte-moi!**

Pour cet exercice, tu devais vérifier si tu avais un ticket Kerberos non expiré ou en obtenir un. Tu peux le faire en utilisant la commande `klist`.

**Exercice 04 : midLS**

Pour cet exercice, tu devais créer une commande qui liste les fichiers et les répertoires du répertoire courant, sans les fichiers cachés, ni "." ni "..". Pour cela, tu peux utiliser la commande `ls -p | grep -v /`.

**Exercice 05 : GiT commit**

Dans cet exercice, tu devais créer un script shell qui renvoie les identifiants des 5 derniers commits de ton dépôt git. Pour cela, tu peux utiliser la commande `git log --pretty=format:'%h' -n 5`.

**Exercice 06 : gitignore**

Ici, tu devais créer un script shell qui renvoie la liste des fichiers ignorés par ton dépôt git. Tu peux le faire en utilisant la commande `git ls-files --others --ignored --exclude-standard`.

**Exercice 07 : diff**

Cet exercice demandait de créer un fichier qui, lorsqu'il est comparé à un autre fichier donné, produit un certain ensemble de différences. Pour cela, tu peux utiliser la commande `diff`.

**Exercice 08 : clean**

Ici, tu devais créer une commande qui trouve et supprime tous les fichiers qui se terminent par ~, ou qui commencent et se terminent par #. Pour cela, tu peux utiliser la commande `find . -name "*~" -o -name "#*#" -delete`.

**Exercice 09 : Illusions, not tricks, Michael...**

Pour cet exercice, tu devais créer un fichier magique qui détecte les fichiers de type "42 file" avec la chaîne "42" au 42ème octet. Tu peux le faire en utilisant la commande `file`.

J'espère que ces explications t'aident à comprendre les différentes commandes utilisées dans ces exercices, cousin! Si t'as d'autres questions, n'hésite pas à demander.

```
# sur ft_magic
41 string 42 42 file

# sur le test
1234567890123456789012345678901234567890142

## et puis la vérification

file -m ft_magic test

## output:
test: 42 file
```