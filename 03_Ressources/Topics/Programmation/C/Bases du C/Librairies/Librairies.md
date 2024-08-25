@ voir aussi : [[__Liste des fonctions]]


## 1. stdio.h (Standard Input/Output)
Comme j'te l'ai dit, c'est la base. Il te faut ça pour discuter avec ton programme.

- `printf`: affiche ce que tu veux.
- `scanf`: prend ce que tu donnes.
- `getchar`: lit un caractère à la fois.
- `putchar`: écrit un caractère à la fois.
- `fgets`: lit une ligne entière, mon gars.
- `fputs`: écrit une ligne entière.

## 2. stdlib.h (STanDard LIBrary)
C'est une autre biblio de base. Elle fait un tas de trucs.

- [[malloc]] et [[free]]: pour louer et libérer de la mémoire.
- [[atoi]] et `atof`: pour transformer les strings en nombres.
- `rand`: pour obtenir des nombres aléatoires.
- `qsort`: pour trier tes trucs.

## 3. string.h
Si tu bosses avec des strings, cette biblio est pour toi.

- [[strcpy]] et [[strncpy]]: pour copier des strings.
- `strcat` et `strncat`: pour coller des strings ensemble.
- `strlen`: pour connaître la taille d'un string.
- `strcmp` et `strncmp`: pour comparer deux strings.

## 4. math.h
Si tu veux faire du calcul sérieux, frérot, tu vas avoir besoin de ça.

- `pow`: pour élever un nombre à une puissance.
- `sqrt`: pour prendre la racine carrée.
- `sin`, `cos`, `tan`: pour faire de la trigonométrie.
- `log` et `exp`: pour bosser avec les logarithmes et les exponentielles.

## 5. time.h
Si tu veux faire du temps ton esclave, cette biblio est pour toi.

- `time`: pour connaître l'heure actuelle.
- `ctime`: pour transformer l'heure en string.
- `strftime`: pour formater l'heure comme tu veux.
- `sleep`: pour faire dormir ton programme.

## 6. ctype.h
Si tu veux bosser avec des caractères, cette biblio a tout ce qu'il te faut.

- `isdigit`, `isalpha`, `islower`, `isupper`: pour vérifier le type d'un caractère.
- `tolower`, `toupper`: pour changer la casse d'un caractère.





Ok, cousin, c'est parti. Les `%` que tu vois dans `printf` et `scanf`, c'est des spécificateurs de format. Ils te permettent de foutre des variables dans tes chaînes de caractères. Voici les plus courants :

1. `%d` ou `%i`: pour un entier signé.
2. `%u`: pour un entier non signé.
3. `%f`: pour un float.
4. `%c`: pour un caractère.
5. `%s`: pour une chaîne de caractères.
6. `%p`: pour une adresse mémoire, frérot.
7. `%%`: pour foutre un vrai `%` dans ta chaîne.


## 1. stdio.h
- `printf` et `scanf`: Ces mecs utilisent des spécificateurs de format avec des `%`. Ils te permettent de foutre des variables dans ta chaîne ou d'en prendre. Y a plein de spécificateurs de format, comme `%d` pour un entier, `%f` pour un float, `%c` pour un caractère, `%s` pour une chaîne et plein d'autres. Tu peux aussi ajouter des précisions avec des nombres après le `%`.

- `getchar` et `putchar`: Ces bad boys travaillent avec un caractère à la fois. Si tu veux entrer un texte caractère par caractère, `getchar` est ton gars. Si tu veux afficher un caractère à la fois, `putchar` est là pour toi.

- `fgets` et `fputs`: Ces gars sont comme `getchar` et `putchar`, mais pour des lignes entières. Ils sont plus sûrs parce qu'ils prennent en compte la taille de ta chaîne.

## 2. stdlib.h
- `malloc` et `free`: Ces mecs sont les rois de la mémoire. `malloc` achète un bout de mémoire pour toi et `free` le rend quand t'en as plus besoin.

- `atoi` et `atof`: Ces gars sont des magiciens. Ils prennent un string et le transforment en nombre. `atoi` fait des entiers et `atof` fait des floats.

- `rand` et `srand`: Si tu veux jouer à la loterie, ces gars sont pour toi. `rand` te donne un nombre aléatoire et `srand` change les numéros pour que tu ne gagnes pas à chaque fois.

- `qsort`: Ce mec est un monstre de l'organisation. Il prend un tas de trucs et les met en ordre pour toi. Il te suffit de lui dire comment comparer deux trucs et il s'occupe du reste.

## 3. string.h
- `strcpy`, `strncpy`, `strcat`, `strncat`: Ces gars sont les bouchers de la biblio. Ils prennent des morceaux de strings et les collent ensemble. Les versions avec `n` sont plus sûres parce qu'elles prennent en compte la taille de ta chaîne.

- `strlen`: Ce mec est comme un mètre ruban. Il mesure la taille d'un string pour toi.

- `strcmp` et `strncmp`: Ces gars sont des juges. Ils comparent deux strings et te disent lequel est le plus grand. Les versions avec `n` sont plus sûres parce qu'elles prennent en compte la taille de ta chaîne.

