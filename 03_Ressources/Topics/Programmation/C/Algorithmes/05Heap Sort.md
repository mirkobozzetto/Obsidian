
🔥 le **Heap Sort** ou tri par tas, frérot ! C'est un algorithme de tri qui utilise une structure de données appelée tas. Le tas est une sorte d'arbre binaire équilibré qui maintient l'ordre des éléments.

Le **Heap Sort** a été inventé par J. W. J. Williams en 1964. Ce type de tri est très efficace et est utilisé dans beaucoup de domaines, par exemple pour gérer les priorités dans les systèmes d'exploitation, pour les algorithmes de graphes comme Dijkstra et Prim, et même pour le tri de gros volumes de données.

Son principe est simple :

1️⃣ On transforme le tableau en un tas (max heap).
2️⃣ On supprime successivement le plus grand élément du tas et on le place à la fin du tableau.
3️⃣ On répète ces étapes jusqu'à ce que le tas soit vide.

Passons maintenant au code pour visualiser tout ça, mon pote ! 💻

```c
#include <stdio.h>

void swap(int *a, int *b) {
    int t = *a;
    *a = *b;
    *b = t;
}

void heapify(int arr[], int n, int i) {
    int max = i;
    int leftChild = 2 * i + 1;
    int rightChild = 2 * i + 2;

    if (leftChild < n && arr[leftChild] > arr[max])
        max = leftChild;

    if (rightChild < n && arr[rightChild] > arr[max])
        max = rightChild;

    if (max != i) {
        swap(&arr[i], &arr[max]);
        heapify(arr, n, max);
    }
}

void heapSort(int arr[], int n) {
    for (int i = n / 2 - 1; i >= 0; i--)
        heapify(arr, n, i);

    for (int i = n - 1; i >= 0; i--) {
        swap(&arr[0], &arr[i]);
        heapify(arr, i, 0);
    }
}

void printArray(int arr[], int n) {
    for (int i = 0; i < n; ++i)
        printf("%d ", arr[i]);
    printf("\n");
}

int main() {
    int arr[] = {11, 34, 9, 5, 16, 10};
    int n = sizeof(arr) / sizeof(arr[0]);

    printf("Avant le tri, cousin : ");
    printArray(arr, n);

    heapSort(arr, n);

    printf("Après le tri, frérot : ");
    printArray(arr, n);
}
```

Dans ce code, la fonction `heapify` est utilisée pour maintenir la propriété du tas max. Elle compare un élément avec ses deux enfants et place le plus grand des trois en haut. Si les enfants sont plus grands, ils sont échangés avec le parent et `heapify` est appelé récursivement.

La fonction `heapSort` utilise `heapify` pour transformer le tableau en tas, puis elle échange le premier élément (le max) avec le dernier, réduit la taille du tas de 1 et appelle `heapify` sur le nouveau tas. Elle répète ces étapes jusqu'à ce que le tas soit vide.

