
Voilà un petit exercice pour te familiariser avec les matrices. On va simplement créer une matrice 3x3 (c'est-à-dire avec 3 lignes et 3 colonnes), la remplir avec des nombres et l'afficher.

```c
#include <stdio.h>

int main()
{
    int matrix[3][3];
    int count = 1;
    
    // On remplit la matrice avec des nombres.
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            matrix[i][j] = count;
            count++;
        }
    }
    
    // On affiche la matrice.
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            printf("%d ", matrix[i][j]);
        }
        printf("\n");
    }
    
    return 0;
}
```

Ce code va afficher la matrice suivante :

```
1 2 3
4 5 6
7 8 9
```

Comme tu peux le voir, le numéro de la ligne et de la colonne détermine la valeur dans la matrice. On commence à compter à partir de 1, et on augmente le compteur à chaque fois qu'on ajoute une valeur dans la matrice.

C'est assez simple, mais ça te donne une idée de la façon dont on peut manipuler des matrices en C. Tu peux jouer avec le code pour te familiariser davantage avec les matrices, essayer de remplir la matrice avec d'autres valeurs, ou essayer de créer une matrice plus grande. À toi de jouer, frérot! 🚀


Voilà une variante du code précédent qui utilise des boucles `while` et qui demande à l'utilisateur de spécifier les dimensions de la matrice.

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    int rows, cols;
    printf("Entre le nombre de lignes de ta matrice: ");
    scanf("%d", &rows);
    printf("Entre le nombre de colonnes de ta matrice: ");
    scanf("%d", &cols);
    
    // On alloue dynamiquement de la mémoire pour la matrice.
    int **matrix = (int **)malloc(rows * sizeof(int *));
    for (int i = 0; i < rows; i++)
        matrix[i] = (int *)malloc(cols * sizeof(int));
    
    int count = 1;
    int i = 0, j = 0;
    
    // On remplit la matrice avec des nombres.
    while (i < rows)
    {
        j = 0;
        while (j < cols)
        {
            matrix[i][j] = count;
            count++;
            j++;
        }
        i++;
    }
    
    // On affiche la matrice.
    i = 0;
    while (i < rows)
    {
        j = 0;
        while (j < cols)
        {
            printf("%d ", matrix[i][j]);
            j++;
        }
        printf("\n");
        i++;
    }
    
    // On libère la mémoire allouée pour la matrice.
    for (i = 0; i < rows; i++)
        free(matrix[i]);
    free(matrix);
    
    return 0;
}
```

Dans ce code, on utilise `malloc` pour allouer dynamiquement de la mémoire pour la matrice en fonction du nombre de lignes et de colonnes que l'utilisateur a spécifié. Ensuite, on utilise des boucles `while` pour remplir et afficher la matrice. Finalement, on libère la mémoire allouée pour la matrice avec `free`.

Fais gaffe, frérot! 🚨 Avec `malloc`, si tu oublies de libérer la mémoire, ton programme peut causer ce qu'on appelle une "fuite de mémoire", ce qui n'est pas cool. Faut toujours penser à nettoyer après soi! 🧹

Et voilà! Tu peux maintenant créer des matrices de n'importe quelle taille en C! 🎉🚀

