
On va maintenant s'attaquer à un autre algorithme de tri assez célèbre : le **Insertion Sort** (tri par insertion). 

C'est comme quand tu joues aux cartes et que tu tri les cartes dans ta main une par une. Tu commences par la deuxième carte. Si elle est plus petite que la première, tu la mets avant. Sinon, tu la laisses où elle est. Ensuite, tu passes à la troisième carte, et tu la compares à celles qui sont avant. Tu la déplaces à l'endroit approprié pour qu'elle soit triée par rapport à celles avant elle. Tu continues à faire ça jusqu'à ce que toutes les cartes soient triées.

Jette un coup d'œil au code, frérot. 

```c
#include <stdio.h>

void insertionSort(int arr[], int n)
{
   int i, key, j;
   for (i = 1; i < n; i++)
   {
       key = arr[i];
       j = i - 1;
       while (j >= 0 && arr[j] > key)
       {
           arr[j + 1] = arr[j];
           j = j - 1;
       }
       arr[j + 1] = key;
   }
}

int main()
{
    int arr[] = {12, 11, 13, 5, 6};
    int n = sizeof(arr) / sizeof(arr[0]);
    insertionSort(arr, n);
    printf("Sorted array is: \n");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
    return 0;
}
```

On commence par le deuxième élément de notre tableau (clé = arr[i]). On le compare avec les éléments avant lui (j = i - 1). Si l'élément est plus grand que la clé, on le déplace d'un cran vers la droite. On continue à faire ça jusqu'à ce qu'on trouve un élément qui est inférieur à la clé, ou jusqu'à ce qu'on atteigne le début du tableau. À ce moment-là, on insère la clé.

On répète le processus pour tous les éléments du tableau, et à la fin, le tableau est trié! 🚀💪

----

On va demander à l'utilisateur d'entrer des chiffres jusqu'à ce qu'il saisisse autre chose que des chiffres. On va utiliser la fonction scanf qui retourne le nombre de valeurs correctement lues et affectées. Si cette valeur est différente de 1 (ce qui signifie qu'un chiffre n'a pas été lu), on arrête de lire l'entrée.

Voici comment on pourrait faire :

```c
#include <stdio.h>

void insertionSort(int arr[], int n)
{
   int i, key, j;
   for (i = 1; i < n; i++)
   {
       key = arr[i];
       j = i - 1;
       while (j >= 0 && arr[j] > key)
       {
           arr[j + 1] = arr[j];
           j = j - 1;
       }
       arr[j + 1] = key;
   }
}

int main()
{
    int arr[1000];
    int n = 0;
    int val;
    printf("Entre les éléments (un non-chiffre pour terminer) : ");
    while(scanf("%d", &val) == 1)
    {
        arr[n++] = val;
        if(n >= 1000)
        {
            printf("Désolé frérot, on ne peut pas gérer plus de 1000 éléments!\n");
            break;
        }
    }
    insertionSort(arr, n);
    printf("Les éléments triés sont : \n");
    for (int i = 0; i < n; i++)
        printf("%d ", arr[i]);
    return 0;
}
```

Ici, on utilise un tableau de 1000 éléments, donc on ne peut pas gérer plus de 1000 entrées. Si tu veux en gérer plus, tu devras augmenter la taille de ce tableau ou utiliser une allocation dynamique de la mémoire (ce qui est un peu plus avancé et sort de la portée de cet exemple). 😉

N'oublie pas qu'on ne peut pas entrer des mots ou des caractères autres que des chiffres, sinon le programme arrêtera de lire l'entrée, considérant que c'est le signal que l'utilisateur a terminé d'entrer les chiffres. 🛠️


OK cousin, je vais te montrer un exemple de test avec cet algorithme. Imaginons que tu entres les chiffres suivants : `9 4 8 2 6 5 3 7 1 0`. Et ensuite, tu décides de mettre fin à l'entrée en tapant un caractère qui n'est pas un chiffre, disons 'q'. Voici comment cela se déroule :

```
Entre les éléments (un non-chiffre pour terminer) : 9 4 8 2 6 5 3 7 1 0 q
```

Maintenant, voyons comment l'algo va bouger tes chiffres pour les mettre en ordre croissant, étape par étape :

```
Entrée : 9 4 8 2 6 5 3 7 1 0
1ère itération : 4 9 8 2 6 5 3 7 1 0
2ème itération : 4 8 9 2 6 5 3 7 1 0
3ème itération : 2 4 8 9 6 5 3 7 1 0
4ème itération : 2 4 6 8 9 5 3 7 1 0
5ème itération : 2 4 5 6 8 9 3 7 1 0
6ème itération : 2 3 4 5 6 8 9 7 1 0
7ème itération : 2 3 4 5 6 7 8 9 1 0
8ème itération : 1 2 3 4 5 6 7 8 9 0
9ème itération : 0 1 2 3 4 5 6 7 8 9
```

Et voilà l'output que tu verras :

```
Les éléments triés sont : 
0 1 2 3 4 5 6 7 8 9 
```

Donc avec cet algo, on est passé d'une entrée complètement en désordre à une sortie bien ordonnée, comme une file d'attente bien organisée, wesh! 📊👍