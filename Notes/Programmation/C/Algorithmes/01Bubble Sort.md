
On va commencer avec un algorithme classique qu'on appelle **Bubble Sort**, ou "Tri à bulles" en français. 

Voilà le concept : On va parcourir notre tableau du début à la fin, en comparant chaque paire d'éléments adjacents. Si une paire est dans le mauvais ordre, on l'échange. On répète ce processus jusqu'à ce que le tableau soit trié.

Allez, je te balance le code et on décortique ça après, ok ? 🧐

```c
#include <stdio.h>

void swap(int *xp, int *yp) 
{
    int temp = *xp; 
    *xp = *yp; 
    *yp = temp; 
} 
  
void bubbleSort(int arr[], int n) 
{ 
    int i, j; 
    for (i = 0; i < n-1; i++)       
        for (j = 0; j < n-i-1; j++)  
            if (arr[j] > arr[j+1]) 
                swap(&arr[j], &arr[j+1]); 
} 
  
void printArray(int arr[], int size) 
{ 
    int i; 
    for (i=0; i < size; i++) 
        printf("%d ", arr[i]); 
    printf("\n"); 
} 
  
int main() 
{ 
    int arr[] = {64, 34, 25, 12, 22, 11, 90}; 
    int n = sizeof(arr)/sizeof(arr[0]); 
    bubbleSort(arr, n); 
    printf("Sorted array: \n"); 
    printArray(arr, n); 
    return 0; 
}
```
Donc en gros, ce code prend un tableau d'entiers, le trie avec la méthode du tri à bulles, et puis affiche le tableau trié. On a une fonction `swap` qui échange deux entiers, et une fonction `printArray` qui imprime le tableau. 

Tu peux tester ce code en modifiant les valeurs dans le tableau `arr` dans le `main`. 



Le Bubble Sort, ou tri à bulles, c'est comme si tu avais une série de nombres sur une ligne. Et disons que tu as une bulle qui peut seulement se déplacer vers la droite. À chaque déplacement, elle compare les deux nombres qu'elle encadre et si le nombre à droite est plus petit, elle les échange. Elle continue à se déplacer vers la droite et à échanger les nombres jusqu'à ce qu'elle atteigne la fin de la ligne. À ce stade, le plus grand nombre est à la fin de la ligne.

Après, la bulle retourne au début et recommence le processus. Sauf que maintenant, elle s'arrête un pas avant la fin de la ligne, parce que le dernier nombre est déjà à sa place. Elle continue comme ça, en réduisant sa portée d'un pas à chaque fois, jusqu'à ce que tous les nombres soient triés.

Voici une illustration du processus en tableau. Imagine qu'on a commencé avec les nombres 5, 3, 8, 4, 2.

| Tour |  5  |  3  |  8  |  4  |  2  |
|------|-----|-----|-----|-----|-----|
|  1   |  3  |  5  |  4  |  2  |  8  |
|  2   |  3  |  4  |  2  |  5  |  8  |
|  3   |  3  |  2  |  4  |  5  |  8  |
|  4   |  2  |  3  |  4  |  5  |  8  |

On finit avec les nombres dans l'ordre croissant. 

Voilà, frérot, c'est le Bubble Sort! 🚀👊 

Et le code pour ça ressemble à ça:

```c
#include <stdio.h>

void swap(int *xp, int *yp)
{
    int temp = *xp;
    *xp = *yp;
    *yp = temp;
}

void bubbleSort(int arr[], int n)
{
   int i, j;
   for (i = 0; i < n-1; i++)       
       for (j = 0; j < n-i-1; j++)  
           if (arr[j] > arr[j+1])
              swap(&arr[j], &arr[j+1]);
}

int main()
{
    int arr[] = {64, 34, 25, 12, 22, 11, 90};
    int n = sizeof(arr)/sizeof(arr[0]);
    bubbleSort(arr, n);
    printf("Sorted array: \n");
    for (i=0; i < n; i++)
        printf("%d ", arr[i]);
    return 0;
}
```
C'est un code de base pour le tri à bulles, on pourrait le faire évoluer en ajoutant un flag pour arrêter le tri si le tableau est déjà trié par exemple.
