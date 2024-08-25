

Bon, on va passer à un autre algo maintenant. Je te présente le **tri par sélection** (ou "selection sort" en anglais), cousin. C'est encore un autre moyen de trier des données, mais il a une petite spécificité : au lieu de juste bouger les trucs autour, il cherche l'élément le plus petit (ou le plus grand, ça dépend de ce que tu veux faire) et le place au début. On répète ça jusqu'à ce que tout soit trié.

Tiens, voilà le code en C pour cet algo :

```c
#include <stdio.h>

void swap(int *xp, int *yp)
{
    int temp = *xp;
    *xp = *yp;
    *yp = temp;
}

void selectionSort(int arr[], int n)
{
    int i, j, min_idx;

    for (i = 0; i < n-1; i++)
    {
        min_idx = i;
        for (j = i+1; j < n; j++)
            if (arr[j] < arr[min_idx])
                min_idx = j;

        swap(&arr[min_idx], &arr[i]);
    }
}

int main()
{
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr)/sizeof(arr[0]);
    selectionSort(arr, n);
    printf("Sorted array: \n");
    for (int i=0; i < n; i++)
        printf("%d ", arr[i]);
    printf("\n");
    return 0;
}
```

Et maintenant, on va le décortiquer, frérot !

Au début, on a un tableau pas trié :

```
64 25 12 22 11
```

On commence par trouver le plus petit nombre dans le tableau. Ici, c'est 11. On l'échange avec le premier élément du tableau :

```
11 25 12 22 64
```

On fait la même chose avec le reste du tableau. Le plus petit nombre maintenant, c'est 12. On l'échange avec le deuxième élément :

```
11 12 25 22 64
```

Et on continue comme ça jusqu'à ce que tout soit bien trié. À la fin, on se retrouve avec ça :

```
11 12 22 25 64
```

Voilà, c'est tout propre ! 🧹✨

La grosse différence avec le tri à bulles, c'est que le tri par sélection fait moins d'échanges. Du coup, si t'as un tas de données à trier et que tu veux faire ça vite fait, c'est un bon choix. Mais attention, frérot, ça reste un algo basique. Y'a des trucs plus balèzes pour trier des données plus compliquées. Mais pour commencer, c'est nickel 👌
