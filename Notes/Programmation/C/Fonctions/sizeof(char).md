La taille d'un type de données `char` en C est garantie d'être de 1 octet. Cela signifie que `sizeof(char)` renverra toujours 1.

Le type `char` en C est utilisé pour représenter un seul caractère, généralement codé selon le jeu de caractères ASCII ou Unicode. La taille d'un `char` étant de 1 octet, cela signifie qu'il occupe la plus petite unité de mémoire adressable dans la plupart des systèmes.

Voici un exemple d'utilisation de `sizeof(char)` :

```c
#include <stdio.h>

int main() {
    printf("Taille de char : %zu octets\n", sizeof(char));
    return 0;
}
```

Dans cet exemple, la fonction `printf` est utilisée pour afficher la taille d'un `char` en octets à l'aide de `sizeof(char)`.

Il est important de noter que la taille d'un `char` étant toujours de 1 octet, vous n'avez généralement pas besoin d'utiliser `sizeof(char)` explicitement dans votre code. Cependant, `sizeof(char)` peut être utile lorsque vous travaillez avec des types de données de taille différente pour lesquels vous souhaitez connaître la taille en octets.