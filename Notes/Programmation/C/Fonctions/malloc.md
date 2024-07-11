💡 La fonction `malloc` est un acronyme en anglais qui signifie "memory allocation" (allocation de mémoire).

La fonction `malloc` en C est utilisée pour allouer dynamiquement de la mémoire. Elle fait partie de la bibliothèque standard du langage C et est définie dans l'en-tête `stdlib.h`.

Voici le prototype de la fonction `malloc` :

```c
void *malloc(size_t size);
```

La fonction `malloc` prend en argument un paramètre `size` de type `size_t`, qui représente la quantité de mémoire à allouer en octets. Elle renvoie un pointeur de type `void *` vers le début de la mémoire allouée.

Voici un exemple d'utilisation de la fonction `malloc` :

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int *ptr = (int *)malloc(sizeof(int));

    if (ptr != NULL) {
        *ptr = 10;

        printf("Valeur : %d\n", *ptr);

        free(ptr);  // Libération de la mémoire allouée
    }

    return 0;
}
```

Dans cet exemple, la fonction `malloc` est utilisée pour allouer dynamiquement de la mémoire pour un entier. La taille de la mémoire allouée est spécifiée à l'aide de [[sizeof(int)]], qui renvoie la taille en octets d'un entier. Le pointeur `ptr` est utilisé pour stocker l'adresse de la mémoire allouée. Ensuite, la mémoire allouée est utilisée pour stocker la valeur `10`. Finalement, la fonction [[free]] est appelée pour libérer la mémoire allouée.

Il est important de noter que `malloc` peut échouer si la mémoire demandée n'est pas disponible. Dans ce cas, la fonction renverra un pointeur nul (`NULL`). Par conséquent, il est nécessaire de vérifier si la valeur retournée par `malloc` est différente de `NULL` avant d'utiliser la mémoire allouée.

Après avoir alloué de la mémoire à l'aide de `malloc`, vous devez vous assurer de libérer cette mémoire en appelant la fonction [[free]] une fois que vous avez terminé de l'utiliser. Cela permet de prévenir les fuites de mémoire et d'optimiser l'utilisation des ressources système.