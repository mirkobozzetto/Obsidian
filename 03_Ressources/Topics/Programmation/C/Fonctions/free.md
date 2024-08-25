
La fonction `free` en C est utilisée pour libérer la mémoire qui a été précédemment allouée dynamiquement à l'aide des fonctions telles que [[malloc]], [[calloc]] ou [[realloc]]. Elle fait partie de la bibliothèque standard du langage C et est définie dans l'en-tête `stdlib.h`.

Voici le prototype de la fonction `free` :

```c
void free(void *ptr);
```

La fonction `free` prend en argument un pointeur `ptr` vers la mémoire précédemment allouée à l'aide des fonctions d'allocation de mémoire. Lorsque vous appelez `free(ptr)`, la mémoire associée à `ptr` est libérée et peut être réutilisée par le système pour d'autres allocations de mémoire.

Il est important de noter que `ptr` doit être un pointeur valide retourné par une fonction d'allocation de mémoire et ne doit pas être déjà libéré. De plus, vous ne devez pas utiliser `ptr` après avoir appelé `free` car son comportement devient indéfini.

Voici un exemple d'utilisation de la fonction `free` :

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

Dans cet exemple, la fonction `malloc` est utilisée pour allouer dynamiquement de la mémoire pour un entier. Ensuite, la mémoire allouée est utilisée pour stocker la valeur `10`. Finalement, la fonction `free` est appelée pour libérer la mémoire allouée.

Il est essentiel de libérer correctement la mémoire allouée dynamiquement avec `free` une fois que vous avez terminé de l'utiliser. Cela évite les fuites de mémoire et permet au système de récupérer l'espace mémoire pour une utilisation future.