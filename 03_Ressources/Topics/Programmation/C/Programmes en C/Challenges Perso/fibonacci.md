[[atoi]]
[[typedef]]
[[struct]]

Voici le pseudo-code qui explique le programme en détail :

```
Définir une structure t_data avec trois membres : t1, t2 et next_term.

Créer une fonction s_putchar qui écrit un seul caractère à la sortie standard.

Créer une fonction s_putstr qui écrit une chaîne de caractères à la sortie standard.

Créer une fonction s_putnbr qui affiche un nombre entier à la sortie standard :
- Si le nombre est 0, afficher '0'.
- Si le nombre est négatif, afficher '-' et appeler s_putnbr avec le nombre positif.
- Si le nombre a plus d'un chiffre, appeler s_putnbr avec le nombre divisé par 10 et le reste de la division par 10.
- Sinon, afficher le nombre.

Créer une fonction s_atoi qui convertit une chaîne de caractères en nombre entier :
- Parcourir chaque caractère de la chaîne.
- Si le caractère est un chiffre, le multiplier par 10 et l'ajouter au résultat.
- Sinon, renvoyer -1.
- Renvoyer le résultat à la fin.

Créer une fonction fibonacci qui affiche la suite de Fibonacci jusqu'au n-ième terme :
- Déclarer une variable de type t_data.
- Initialiser t1 à 0 et t2 à 1.
- Pour i allant de 1 à n, faire :
  - Si i n'est pas égal à 1, afficher ", ".
  - Afficher t1.
  - Calculer le prochain terme comme la somme de t1 et t2.
  - Mettre à jour t1 avec la valeur de t2 et t2 avec la valeur du prochain terme.

Dans le main :
- Vérifier s'il y a exactement 2 arguments (le nom du programme et le nombre n).
- Si oui, convertir le second argument en nombre entier avec s_atoi.
- Si le nombre est supérieur à 0, appeler la fonction fibonacci avec ce nombre.
```

En gros, ce programme affiche la suite de Fibonacci jusqu'au n-ième terme, où n est l'argument passé au programme. Il vérifie que l'argument est bien un nombre entier positif avant d'appeler la fonction fibonacci. La suite de Fibonacci est générée en utilisant une structure pour stocker les deux derniers termes et le prochain terme à chaque itération.


```c
#include <unistd.h>

typedef struct s_data
{
    int t1;
    int t2;
    int next_term;
} t_data;

void s_putchar(char c)
{
    write(1, &c, 1);
}

void s_putstr(char *str)
{
    while (*str)
        s_putchar(*str++);
}

void s_putnbr(int n)
{
    if (n == 0)
    {
        s_putchar('0');
        return;
    }
    if (n < 0)
    {
        s_putchar('-');
        n = -n;
    }
    if (n / 10)
        s_putnbr(n / 10);
    s_putchar((n % 10) + '0');
}

int s_atoi(char *str)
{
    int res = 0;

    while (*str)
    {
        if (*str >= '0' && *str <= '9')
        {
            res = res * 10 + (*str - '0');
            str++;
        }
        else
            return (-1);
    }
    return (res);
}

void fibonacci(int n)
{
    t_data data;

    data.t1 = 0;
    data.t2 = 1;

    int i = 1;
    while (i <= n)
    {
        if (i != 1)
            s_putstr(", ");
        s_putnbr(data.t1);
        data.next_term = data.t1 + data.t2;
        data.t1 = data.t2;
        data.t2 = data.next_term;
        
        i++;
    }
}


int main(int argc, char **argv)
{
    int n;

    if (argc == 2)
    {
        n = s_atoi(argv[1]);
        if (n > 0)
            fibonacci(n);
    }
    return (0);
}
```


notes : 
[[typedef]]
La déclaration `typedef struct s_data { int t1; int t2; int next_term; } t_data;` est utilisée pour créer un nouveau type de données appelé `t_data` qui représente une structure contenant les variables `t1`, `t2` et `next_term`. 

La structure `t_data` est utilisée dans la fonction `fibonacci` pour stocker les valeurs nécessaires lors du calcul de la suite de Fibonacci. Les variables `t1` et `t2` représentent respectivement les deux termes précédents de la suite, tandis que `next_term` représente le terme suivant à calculer.

Le fait d'utiliser `typedef` permet de définir un alias (`t_data`) pour le type de données `struct s_data`. Cela rend l'utilisation de la structure plus concise et facilite la manipulation des variables de ce type dans le programme.

Par exemple, grâce à `typedef`, nous pouvons déclarer une variable de type `t_data` simplement en écrivant `t_data data;` au lieu de `struct s_data data;`. Cela simplifie la lecture et l'écriture du code en évitant de répéter le mot-clé `struct` à chaque utilisation de la structure.

En résumé, `typedef struct` est utilisé pour créer un nouveau type de données à partir d'une structure existante, et `t_data` est l'alias que nous utilisons pour se référer à cette structure de manière plus concise dans notre programme.
___

La fonction `s_putnbr` est utilisée pour afficher un nombre entier sur la sortie standard en utilisant la fonction `s_putchar` pour afficher chaque chiffre.

Voici comment fonctionne cette fonction :

1. Si le nombre `n` est égal à zéro, alors on affiche directement le caractère '0' avec `s_putchar('0')` et la fonction se termine.
2. Si le nombre `n` est négatif, on affiche d'abord le caractère '-' avec `s_putchar('-')` pour indiquer qu'il s'agit d'un nombre négatif. Ensuite, on change `n` en sa valeur absolue en utilisant l'opérateur `-n`.
3. Si le nombre `n` a plus d'un chiffre, on effectue une récursion en appelant `s_putnbr(n / 10)` pour afficher tous les chiffres sauf le dernier. Cela permet d'afficher les chiffres dans l'ordre correct.
4. Enfin, on affiche le dernier chiffre en utilisant `s_putchar((n % 10) + '0')`. L'opération `(n % 10) + '0'` permet de convertir le chiffre en sa représentation ASCII pour pouvoir l'afficher correctement.

En résumé, la fonction `s_putnbr` affiche un nombre entier en séparant chaque chiffre et en le convertissant en caractère ASCII avant de l'afficher à l'aide de la fonction `s_putchar`.
___

Cette fonction `fibonacci` génère la suite de Fibonacci jusqu'au terme `n` et affiche les termes générés.

Voici comment elle fonctionne :

1. On crée une structure `t_data` qui contient trois variables : `t1`, `t2` et `next_term`. `t1` et `t2` sont initialisées respectivement à 0 et 1.

2. On initialise une variable `i` à 1 avant d'entrer dans la boucle `while`.

3. La boucle `while` s'exécute tant que la valeur de `i` est inférieure ou égale à `n`. Cela garantit que le nombre de termes générés correspond à `n`.

4. À chaque itération de la boucle, on vérifie si `i` est différent de 1. Si c'est le cas, on affiche une virgule et un espace pour séparer les termes générés.

5. On affiche ensuite le terme actuel `data.t1` en utilisant la fonction `s_putnbr`.

6. On calcule le prochain terme de la suite de Fibonacci en ajoutant les valeurs actuelles de `data.t1` et `data.t2` et on le stocke dans `data.next_term`.

7. On met à jour les valeurs de `data.t1` et `data.t2` en déplaçant `data.t2` vers `data.t1` et `data.next_term` vers `data.t2`.

8. On incrémente la valeur de `i` de 1 pour passer à l'itération suivante.

9. Une fois que la condition de la boucle `while` n'est plus satisfaite (c'est-à-dire `i > n`), la boucle se termine et la fonction se termine également.

Ainsi, en exécutant cette fonction avec une valeur `n`, la suite de Fibonacci jusqu'au `n`ème terme sera générée et affichée.

Et effectivement, la structure `t_data` est définie dans le code précédent avec la syntaxe suivante :

```c
typedef struct s_data
{
    int t1;
    int t2;
    int next_term;
} t_data;
```

Cette déclaration crée une nouvelle structure nommée `s_data`. Cette structure contient trois membres de type `int` : `t1`, `t2` et `next_term`.

La ligne suivante `t_data;` utilise le `typedef` pour définir un nouveau type `t_data` basé sur la structure `s_data`. Cela permet d'utiliser `t_data` comme un type de données à part entière sans avoir à répéter `struct s_data` à chaque fois que nous voulons déclarer une variable de ce type.

En d'autres termes, après avoir défini cette structure et son type associé, nous pouvons créer des variables de type `t_data` et accéder à ses membres (`t1`, `t2` et `next_term`) pour stocker et manipuler des données liées à la suite de Fibonacci dans notre programme.
___


Dans un programme en C, la fonction `main` peut prendre deux arguments : `int argc` et `char **argv`. Ces deux arguments sont utilisés pour récupérer les arguments de la ligne de commande qui sont passés au programme lorsque celui-ci est exécuté.

- `argc` est le "argument count" (compte des arguments). Il représente le nombre d'arguments qui ont été passés au programme. Par défaut, `argc` est toujours au moins 1, car le nom du programme lui-même est considéré comme le premier argument.

- `argv` est le "argument vector" (vecteur des arguments). Il s'agit d'un tableau de chaînes de caractères (plus précisément, un tableau de pointeurs sur des `char`), où chaque chaîne représente un argument distinct passé au programme. Par exemple, `argv[0]` est le nom du programme, `argv[1]` est le premier argument passé au programme, etc.

Dans ce contexte, `if (argc == 2)` vérifie si exactement deux arguments ont été passés au programme (le nom du programme et un autre argument). Si c'est le cas, le bloc de code à l'intérieur des accolades `{}` est exécuté.

Dans ce bloc, `n = s_atoi(argv[1]);` convertit le premier argument passé au programme (qui est une chaîne de caractères) en un entier, en utilisant la fonction `s_atoi` (qui est une variante de la fonction standard `atoi` de la bibliothèque C).

Ensuite, `if (n > 0)` vérifie si cet entier est supérieur à zéro. Si c'est le cas, la fonction `fibonacci` est appelée avec `n` comme argument.
