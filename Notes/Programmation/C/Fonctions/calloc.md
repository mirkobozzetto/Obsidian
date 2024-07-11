💡 La fonction `calloc` est également un acronyme en anglais qui signifie "clear allocation" ou "contiguous allocation" en fonction des sources.

La fonction `calloc` en C est utilisée pour allouer dynamiquement de la mémoire et initialiser tous les octets à zéro. Elle fait partie de la bibliothèque standard du langage C et est définie dans l'en-tête `stdlib.h`.

Voici le prototype de la fonction `calloc` :

```c
void *calloc(size_t num_elements, size_t element_size);
```

La fonction `calloc` prend en argument `num_elements`, qui représente le nombre d'éléments à allouer, et `element_size`, qui représente la taille de chaque élément en octets. Elle renvoie un pointeur de type `void *` vers le début de la mémoire allouée et initialisée à zéro.

Voici un exemple d'utilisation de la fonction `calloc` :

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int num_elements = 5;
    int element_size = sizeof(int);

    int *ptr = (int *)calloc(num_elements, element_size);

    if (ptr != NULL) {
        for (int i = 0; i < num_elements; i++) {
            printf("Valeur à l'indice %d : %d\n", i, ptr[i]);
        }

        free(ptr);  // Libération de la mémoire allouée
    }

    return 0;
}
```

Dans cet exemple, la fonction `calloc` est utilisée pour allouer dynamiquement de la mémoire pour un tableau d'entiers de taille `num_elements`, où chaque entier occupe `element_size` octets. Le pointeur `ptr` est utilisé pour stocker l'adresse de la mémoire allouée. La mémoire allouée par `calloc` est initialisée à zéro, ce qui signifie que tous les éléments du tableau sont initialisés à zéro.

Après avoir alloué de la mémoire à l'aide de `calloc`, vous devez vous assurer de libérer cette mémoire en appelant la fonction [[free]] une fois que vous avez terminé de l'utiliser. Cela permet de prévenir les fuites de mémoire et d'optimiser l'utilisation des ressources système.