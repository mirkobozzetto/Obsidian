
L'opérateur `sizeof` en C est utilisé pour déterminer la taille, en octets, d'un type de données ou d'une variable. L'expression `sizeof(int)` renvoie la taille en octets du type de données `int` sur la plate-forme ou le compilateur spécifique utilisé.

La taille de l'entier `int` peut varier en fonction de l'architecture de la machine et du compilateur utilisé. En général, l'entier `int` occupe généralement 4 octets (32 bits) sur la plupart des systèmes modernes.

Voici un exemple d'utilisation de `sizeof(int)` :

```c
#include <stdio.h>

int main() {
    printf("Taille de int : %zu octets\n", sizeof(int));
    return 0;
}
```

Dans cet exemple, la fonction `printf` est utilisée pour afficher la taille de l'entier `int` en octets. L'opérateur `sizeof(int)` est utilisé pour obtenir la taille en octets du type de données `int` sur la plate-forme ou le compilateur spécifique utilisé.

Il est important de noter que la taille d'un type de données peut varier en fonction de l'implémentation et des spécifications du système. Par conséquent, il est recommandé d'utiliser `sizeof` pour obtenir la taille d'un type de données plutôt que de supposer une taille fixe.