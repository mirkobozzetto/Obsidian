💡 `le terme `atoi` est un acronyme qui signifie "ASCII to integer"`

La fonction `atoi` en C est utilisée pour convertir une chaîne de caractères en un entier de type `int`. Elle fait partie de la bibliothèque standard du langage C et est définie dans l'en-tête `stdlib.h`.

Voici le prototype de la fonction `atoi` :

```c
int atoi(const char *str);
```

La fonction `atoi` prend en argument une chaîne de caractères `str` et renvoie la valeur entière correspondante. Elle interprète les caractères de `str` jusqu'à ce qu'elle rencontre un caractère non numérique ou la fin de la chaîne, puis renvoie l'entier correspondant.

Voici comment la fonction `atoi` fonctionne :

1. Elle ignore tous les caractères de `str` qui ne sont pas des chiffres ou le signe plus/minus (+/-) au début de la chaîne.
2. Elle analyse ensuite les chiffres consécutifs et les convertit en un entier.
3. La fonction s'arrête dès qu'elle rencontre un caractère non numérique ou la fin de la chaîne.
4. Si la chaîne de caractères est vide, ou si le premier caractère non ignoré n'est pas un chiffre ou un signe plus/minus, la fonction renvoie zéro (0).
5. Si la valeur calculée dépasse les limites de la représentation d'un entier (`INT_MAX` ou `INT_MIN`), le comportement est indéfini.

Voici un exemple d'utilisation de la fonction `atoi` :

```c
#include <stdio.h>
#include <stdlib.h>

int main() 
{
    char str[] = "12345";
    int num = atoi(str);
    printf("La valeur entière est : %d\n", num);
    return 0;
}
```

Cet exemple convertit la chaîne de caractères `"12345"` en un entier `12345` à l'aide de la fonction `atoi`, puis l'affiche à l'écran.