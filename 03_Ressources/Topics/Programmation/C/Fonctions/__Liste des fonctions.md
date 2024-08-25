@ voir aussi : [[Librairies]]

🔸 **Entrées/sorties :**

- `printf()`: affiche des données formatées sur la sortie standard (généralement la console).
- `scanf()`: lit des données formatées à partir de l'entrée standard (généralement la console).
- `getchar()`: lit un caractère à partir de l'entrée standard.
- `putchar()`: écrit un caractère sur la sortie standard.
- `puts()`: écrit une chaîne de caractères suivie d'un saut de ligne sur la sortie standard.
- `getchar()`: lit un caractère à partir de l'entrée standard.
- `putchar()`: écrit un caractère sur la sortie standard.
- `puts()`: écrit une chaîne de caractères suivie d'un saut de ligne sur la sortie standard.
- `fgets()`: lit une ligne de texte à partir de l'entrée standard.
- `fprintf()`: écrit des données formatées dans un flux de sortie spécifié

Ces fonctions te permettent d'interagir avec l'utilisateur en affichant des messages, en lisant des données à partir de la console et en écrivant des résultats. Elles sont utilisées pour les entrées/sorties standards. Il existe également des fonctions plus avancées pour la manipulation de fichiers, qui ont été mentionnées précédemment. N'hésite pas à me demander si tu as des questions supplémentaires ou si tu as besoin de plus d'informations sur l'une de ces fonctions !

---



🔸 **Maths :**

- `abs()`: renvoie la valeur absolue d'un nombre entier ou d'un nombre à virgule flottante.
- `sqrt()`: renvoie la racine carrée d'un nombre.
- `pow()`: élève un nombre à une puissance donnée.
- `ceil()`: arrondit un nombre à l'entier supérieur le plus proche.
- `floor()`: arrondit un nombre à l'entier inférieur le plus proche.
- `round()`: arrondit un nombre à l'entier le plus proche.
- `trunc()`: tronque la partie décimale d'un nombre.
- `sin()`, `cos()`, `tan()`: calculent respectivement le sinus, le cosinus et la tangente d'un angle en radians.
- `exp()`: renvoie l'exponentielle d'un nombre.
- `log()`: renvoie le logarithme népérien (base e) d'un nombre.
- `log10()`: renvoie le logarithme décimal (base 10) d'un nombre.
- `rand()`: génère un nombre aléatoire.
- `asinh()`, `acosh()`, `atanh()`: calcule respectivement l'inverse du sinus hyperbolique, l'inverse du cosinus hyperbolique et l'inverse de la tangente hyperbolique d'un nombre.
- `log2()`: calcule le logarithme en base 2 d'un nombre.
- `exp2()`: calcule 2 élevé à la puissance d'un nombre.

Ces fonctions te permettent de réaliser des opérations mathématiques dans ton programme. Elles sont incluses dans la bibliothèque standard de C `math.h`. N'oublie pas d'inclure cette bibliothèque dans ton code si tu utilises ces fonctions.

---

🔸**Gestion des fichiers :**

- `fopen()`: ouvre un fichier et renvoie un pointeur sur la structure FILE associée.
- `fclose()`: ferme un fichier ouvert précédemment.
- `fprintf()`: écrit des données formatées dans un fichier.
- `fscanf()`: lit des données formatées à partir d'un fichier.
- `fgetc()`: lit un caractère à partir d'un fichier.
- `fgets()`: lit une ligne de texte à partir d'un fichier.
- `fputc()`: écrit un caractère dans un fichier.
- `fputs()`: écrit une chaîne de caractères dans un fichier.
- `feof()`: vérifie la fin d'un fichier.
- `rewind()`: replace le curseur de lecture/écriture au début du fichier.
- `ftell()`: renvoie la position actuelle du curseur de lecture/écriture dans le fichier.
- `fseek()`: déplace le curseur de lecture/écriture à une position spécifiée dans le fichier.

Ces fonctions te permettent d'ouvrir, lire, écrire et fermer des fichiers dans ton programme. Elles sont essentielles pour effectuer des opérations de lecture et d'écriture sur des fichiers. N'hésite pas à me demander si tu as des questions supplémentaires ou si tu as besoin de plus d'informations sur l'une de ces fonctions !

---

🔸 **Manipulation de la mémoire**
- `malloc()`: réserve un espace mémoire.
- `calloc()`: réserve un espace mémoire et le remplit de zéros.
- `realloc()`: change la taille de l'espace mémoire déjà réservé.
- `free()`: libère l'espace mémoire réservé.
- `sizeof()`: renvoie la taille d'un type ou d'une variable.

Ces fonctions te permettent de gérer dynamiquement la mémoire lors de l'exécution de ton programme en allouant et en libérant de l'espace mémoire selon les besoins. Il est important d'utiliser ces fonctions avec précaution pour éviter les fuites de mémoire ou les accès invalides. Veille à bien comprendre leur fonctionnement et à les utiliser de manière appropriée.

N'hésite pas à me demander si tu as des questions supplémentaires sur ces fonctions ou si tu as besoin de plus d'informations !

---


🔸 **Chaînes de caractères**
- `strlen()`: renvoie la longueur d'une chaîne de caractères.
- `strcpy()`: copie une chaîne de caractères dans une autre.
- `strncpy()`: copie un certain nombre de caractères d'une chaîne à une autre.
- `strcat()`: concatène (colle) deux chaînes de caractères.
- `strncat()`: concatène un certain nombre de caractères d'une chaîne à une autre.
- `strcmp()`: compare deux chaînes de caractères.
- `strncmp()`: compare un certain nombre de caractères entre deux chaînes.
- `strchr()`: cherche la première occurrence d'un caractère dans une chaîne.
- `strrchr()`: cherche la dernière occurrence d'un caractère dans une chaîne.
- `strstr()`: cherche une sous-chaîne dans une autre chaîne.
- `strdup()`: crée une copie d'une chaîne de caractères.
- `strtok()`: découpe une chaîne en plusieurs sous-chaînes en utilisant un délimiteur.
- `sprintf()`: écrit des données formatées dans une chaîne de caractères.
- - `strcmpi()`: compare deux chaînes de caractères de manière insensible à la casse.
- `stricmp()`: compare deux chaînes de caractères de manière insensible à la casse.
- `strnicmp()`: compare un certain nombre de caractères entre deux chaînes de manière insensible à la casse.
- `strlwr()`: convertit une chaîne de caractères en minuscules.
- `strupr()`: convertit une chaîne de caractères en majuscules.
- `strrev()`: inverse une chaîne de caractères.

Ces fonctions te permettent de manipuler et de travailler avec des chaînes de caractères. Elles sont incluses dans la bibliothèque standard de C `string.h`. N'oublie pas d'inclure cette bibliothèque dans ton code si tu utilises ces fonctions.

En plus des fonctions de conversion de types mentionnées précédemment, il existe également des fonctions spécifiques pour la manipulation des caractères en C. Voici quelques-unes des fonctions couramment utilisées :

- `isalpha()`: vérifie si un caractère est alphabétique.
- `isdigit()`: vérifie si un caractère est un chiffre décimal.
- `isalnum()`: vérifie si un caractère est alphabétique ou numérique.
- `islower()`: vérifie si un caractère est en minuscule.
- `isupper()`: vérifie si un caractère est en majuscule.
- `isspace()`: vérifie si un caractère est un espace.
- `tolower()`: convertit un caractère en minuscule.
- `toupper()`: convertit un caractère en majuscule.

Ces fonctions te permettent de manipuler et de vérifier les propriétés des caractères individuels dans une chaîne de caractères. Elles sont incluses dans la bibliothèque standard de C `ctype.h`. N'oublie pas d'inclure cette bibliothèque dans ton code si tu utilises ces fonctions.


---

🔸 **Conversion de types**
- `tolower()`: convertit un caractère en minuscule.
- `toupper()`: convertit un caractère en majuscule.
- `isalpha()`: vérifie si un caractère est alphabétique.
- `isdigit()`: vérifie si un caractère est un chiffre décimal.
- `isalnum()`: vérifie si un caractère est alphabétique ou numérique.
- `islower()`: vérifie si un caractère est en minuscule.
- `isupper()`: vérifie si un caractère est en majuscule.
- `isspace()`: vérifie si un caractère est un espace.
- `atoi()`: convertit une chaîne de caractères en un entier.
- `atol()`: convertit une chaîne de caractères en un long int.
- `atof()`: convertit une chaîne de caractères en un float.
- `itoa()`: convertit un int en une chaîne de caractères.

Ces fonctions te permettent de convertir des valeurs d'un type à un autre. Elles sont incluses dans la bibliothèque standard de C `stdlib.h`. N'oublie pas d'inclure cette bibliothèque dans ton code si tu utilises ces fonctions.

---

🔸 **Manipulation des bits :**

- `&` (ET logique) : effectue une opération bit à bit ET entre deux valeurs.
- `|` (OU logique) : effectue une opération bit à bit OU entre deux valeurs.
- `^` (OU exclusif logique) : effectue une opération bit à bit OU exclusif entre deux valeurs.
- `~` (NON logique) : effectue une opération bit à bit NON (complément à un) sur une valeur.
- `<<` (décalage gauche) : effectue un décalage à gauche des bits d'une valeur donnée.
- `>>` (décalage droite) : effectue un décalage à droite des bits d'une valeur donnée.
- `&=` (ET logique avec assignation) : effectue une opération bit à bit ET entre deux valeurs et attribue le résultat à la première valeur.
- `|=` (OU logique avec assignation) : effectue une opération bit à bit OU entre deux valeurs et attribue le résultat à la première valeur.
- `^=` (OU exclusif logique avec assignation) : effectue une opération bit à bit OU exclusif entre deux valeurs et attribue le résultat à la première valeur.
- `<<=` (décalage gauche avec assignation) : effectue un décalage à gauche des bits d'une valeur donnée et attribue le résultat à la première valeur.
- `>>=` (décalage droite avec assignation) : effectue un décalage à droite des bits d'une valeur donnée et attribue le résultat à la première valeur.

Ces opérations te permettent de manipuler les bits individuels d'une valeur, d'effectuer des opérations logiques bit à bit et des décalages de bits.

---

🔸 **Dates et heures :**

- `time()` : renvoie le temps écoulé depuis le 1er janvier 1970 en secondes.
- `localtime()` : convertit un temps en secondes en une structure `tm` représentant la date et l'heure locale.
- `gmtime()` : convertit un temps en secondes en une structure `tm` représentant la date et l'heure UTC (temps universel coordonné).
- `strftime()` : formate une date et une heure en fonction d'un modèle spécifié.
- `asctime()` : convertit une structure `tm` en une chaîne de caractères représentant la date et l'heure.
- `mktime()` : convertit une structure `tm` en un temps en secondes.
- `difftime()` : calcule la différence de temps en secondes entre deux instants.
- `ctime()` : convertit un temps en secondes en une chaîne de caractères représentant la date et l'heure, avec le format "Jeu Mois Jour Heure:Minute:Seconde Année".

Ces fonctions te permettent de manipuler les dates et heures, d'obtenir des informations spécifiques (jour, mois, année, heure, etc.) et de formater les dates selon tes besoins.

---
🔸 **Manipulation des tableaux** :

- `memmove()`: copie un bloc de mémoire d'une source vers une destination, même si les deux blocs se chevauchent.
- `bcopy()`: copie un bloc de mémoire d'une source vers une destination, même si les deux blocs se chevauchent.
- `bzero()`: remplit un bloc de mémoire avec des zéros.
- `memcmp()`: compare deux blocs de mémoire pour déterminer s'ils sont égaux.
- `memchr()`: recherche la première occurrence d'un octet spécifié dans un bloc de mémoire.

Ces fonctions sont utiles pour la manipulation avancée des tableaux et la gestion des blocs de mémoire. Elles permettent de copier, remplir, comparer et rechercher des données dans des tableaux de manière efficace.

---

🔸 **Gestion des erreurs **:

- `errno`: une variable globale qui contient le code d'erreur associé à la dernière opération qui a échoué.
- `perror()`: affiche un message d'erreur décrivant l'erreur actuelle en fonction de la valeur de `errno`.
- `strerror()`: renvoie une chaîne de caractères décrivant l'erreur associée à un code d'erreur spécifique.
- `exit()`: termine immédiatement le programme en retournant un code de sortie spécifique.
- `assert()`: vérifie une condition et provoque une terminaison anormale du programme si la condition est fausse.
- `setjmp()` et `longjmp()`: permettent la gestion des sauts non-locaux et peuvent être utilisés pour gérer des erreurs dans certaines situations.

Ces mécanismes et fonctions sont utilisés pour détecter, signaler et gérer les erreurs qui peuvent survenir lors de l'exécution d'un programme en C. Ils permettent de prendre des mesures appropriées en cas d'erreur et d'afficher des messages d'erreur pour faciliter le débogage.



---

