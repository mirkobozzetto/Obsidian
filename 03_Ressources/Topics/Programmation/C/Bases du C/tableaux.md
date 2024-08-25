[[aff_a]]


La manipulation de tableaux avec des pointeurs en C est courante et offre une flexibilité pour accéder et modifier les éléments du tableau. Voici quelques opérations de base :

1. Déclaration d'un tableau : Un tableau est une collection d'éléments du même type. Pour déclarer un tableau d'entiers, par exemple, vous pouvez utiliser la syntaxe suivante : `int tableau[N];`, où `tableau` est le nom du tableau et `N` est la taille du tableau. Vous pouvez également initialiser les éléments du tableau lors de la déclaration, par exemple : `int tableau[] = {1, 2, 3, 4, 5};`, où la taille du tableau est déduite du nombre d'éléments.

2. Accès aux éléments du tableau : Les éléments du tableau sont accessibles en utilisant l'opérateur `[]` suivi de l'indice de l'élément souhaité. Par exemple, pour accéder au troisième élément du tableau `tableau`, vous pouvez utiliser `tableau[2]`, car les indices de tableau commencent à partir de zéro.

3. Manipulation des éléments du tableau avec des pointeurs : Les pointeurs peuvent être utilisés pour accéder et manipuler les éléments du tableau. Lorsqu'un tableau est déclaré, le nom du tableau agit également comme un pointeur constant vers le premier élément du tableau. Par exemple, `tableau` est équivalent à `&tableau[0]`. Ainsi, vous pouvez utiliser un pointeur pour parcourir les éléments du tableau de la manière suivante :

```c
int tableau[] = {1, 2, 3, 4, 5};
int *ptr = tableau;  // Pointeur vers le premier élément du tableau

for (int i = 0; i < 5; i++) 
{
    printf("%d ", *ptr);  // Affiche la valeur de l'élément pointé par le pointeur
    ptr++;  // Déplacement du pointeur vers l'élément suivant
}

// Résultat : 1 2 3 4 5
```

4. Passage de tableaux en tant qu'arguments de fonction : Lorsque vous passez un tableau en tant qu'argument de fonction, vous pouvez soit passer le tableau directement, soit passer un pointeur vers le premier élément du tableau. La taille du tableau peut également être passée en tant qu'argument séparé, car les tableaux en C n'ont pas d'informations de taille intrinsèques. Par exemple :

```c
void afficherTableau(int tableau[], int taille) 
{
    for (int i = 0; i < taille; i++) {
        printf("%d ", tableau[i]);
    }
}

int main(void) 
{
    int tableau[] = {1, 2, 3, 4, 5};
    int taille = sizeof(tableau) / sizeof(tableau[0]);
    afficherTableau(tableau, taille);
    return 0;
}

// Résultat : 1 2 3 4 5
```

En utilisant des pointeurs, vous pouvez également réaliser des opérations plus avancées sur les tableaux, telles que le tri, la recherche, la manipulation dynamique de la taille du tableau, etc. Cependant, il est important de faire attention aux limites du tableau et de s'assurer de ne pas accéder à des éléments en dehors de la plage valide du tableau, car cela peut entraîner un comportement indéfini ou des erreurs de segmentation.

Voici un exemple de manipulation de tableau avec des pointeurs en utilisant la fonction `printf` pour afficher les éléments du tableau :

```c
#include <stdio.h>

void afficherTableau(int *ptr, int taille) 
{
    for (int i = 0; i < taille; i++) {
        printf("%d ", *(ptr + i));  // Affiche la valeur de l'élément pointé par le pointeur décalé
    }
}

int main(void) {
    int tableau[] = {1, 2, 3, 4, 5};
    int taille = sizeof(tableau) / sizeof(tableau[0]);
    afficherTableau(tableau, taille);
    return 0;
}

// Résultat : 1 2 3 4 5
```

Dans cet exemple, la fonction `afficherTableau` prend un pointeur `ptr` vers le premier élément du tableau et la taille du tableau. À l'intérieur de la boucle, on utilise l'opération `*(ptr + i)` pour accéder à chaque élément du tableau en utilisant le pointeur décalé.

Il est important de comprendre que les tableaux en C sont basés sur les pointeurs et que la manipulation des pointeurs permet d'accéder et de modifier les éléments du tableau de manière efficace et flexible. Cependant, il est essentiel de prendre des précautions pour éviter les erreurs liées aux pointeurs, telles que les débordements de tableau ou les accès incorrects à la mémoire.