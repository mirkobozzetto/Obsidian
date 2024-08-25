C'est un algorithme qui divise le problème en sous-problèmes plus petits, les résout indépendamment, et combine leurs solutions pour résoudre le problème original.

Voilà le code en C pour ça :

```c
#include <stdio.h>

void merge(int arr[], int l, int m, int r) {
    int i, j, k;
    int n1 = m - l + 1;
    int n2 = r - m;

    int L[n1], R[n2];

    for (i = 0; i < n1; i++)
        L[i] = arr[l + i];
    for (j = 0; j < n2; j++)
        R[j] = arr[m + 1 + j];

    i = 0; 
    j = 0; 
    k = l; 
    while (i < n1 && j < n2) {
        if (L[i] <= R[j]) {
            arr[k] = L[i];
            i++;
        } else {
            arr[k] = R[j];
            j++;
        }
        k++;
    }

    while (i < n1) {
        arr[k] = L[i];
        i++;
        k++;
    }

    while (j < n2) {
        arr[k] = R[j];
        j++;
        k++;
    }
}

void mergeSort(int arr[], int l, int r) {
    if (l < r) {
        int m = l + (r - l) / 2;

        mergeSort(arr, l, m);
        mergeSort(arr, m + 1, r);

        merge(arr, l, m, r);
    }
}

void printArray(int A[], int size) {
    int i;
    for (i = 0; i < size; i++)
        printf("%d ", A[i]);
    printf("\n");
}

int main() {
    int arr[] = {12, 11, 13, 5, 6, 7};
    int arr_size = sizeof(arr) / sizeof(arr[0]);

    printf("Given array is \n");
    printArray(arr, arr_size);

    mergeSort(arr, 0, arr_size - 1);

    printf("\nSorted array is \n");
    printArray(arr, arr_size);
    return 0;
}
```

Ce code va trier le tableau en utilisant le tri fusion. Au début, on a le tableau non trié, et à la fin, le tableau est trié.


L'intérêt du tri fusion (Merge Sort), c'est qu'il a une complexité temporelle de O(n log n) dans tous les cas : meilleur, moyen et pire. Ça le rend plus efficace sur les grandes listes que des tris comme le tri bulle, le tri insertion ou le tri sélection qui sont en O(n^2) dans le pire des cas. 

En fait, le tri fusion est basé sur le principe "diviser pour régner". Il divise d'abord la liste en deux moitiés, les trie indépendamment puis les fusionne. Cette approche réduit le nombre d'opérations nécessaires pour trier la liste, ce qui peut le rendre plus rapide, surtout pour de grandes listes. 

Donc, en gros, si t'as une petite liste, les autres tris peuvent faire l'affaire et être même plus rapides. Mais si t'as une grosse liste de données à trier, là, le tri fusion devient ton meilleur pote ! 


Tranquille, mon frère, on y va. J'vais faire un code qui va te demander d'entrer tes nombres, et ensuite, il va trier tout ça avec notre tri fusion. T'es prêt ?

```C
#include <stdio.h>
#include <stdlib.h>

void merge(int *arr, int l, int m, int r)
{
	int i, j, k;
	int n1 = m - l + 1;
	int n2 = r - m;

	int L[n1], R[n2];

	for (i = 0; i < n1; i++)
		L[i] = arr[l + i];
	for (j = 0; j < n2; j++)
		R[j] = arr[m + 1+ j];

	i = 0; 
	j = 0;
	k = l;
	while (i < n1 && j < n2)
	{
		if (L[i] <= R[j])
		{
			arr[k] = L[i];
			i++;
		}
		else
		{
			arr[k] = R[j];
			j++;
		}
		k++;
	}

	while (i < n1)
	{
		arr[k] = L[i];
		i++;
		k++;
	}

	while (j < n2)
	{
		arr[k] = R[j];
		j++;
		k++;
	}
}

void mergeSort(int *arr, int l, int r)
{
	if (l < r)
	{
		int m = l+(r-l)/2;
		mergeSort(arr, l, m);
		mergeSort(arr, m+1, r);
		merge(arr, l, m, r);
	}
}

int main()
{
	int arr[1000], num, i;
	
	printf("Combien de nombres tu veux entrer, frérot ? ");
	scanf("%d", &num);
	
	printf("Entre tes nombres maintenant :\n");
	for(i = 0; i < num; i++)
		scanf("%d", &arr[i]);

	mergeSort(arr, 0, num - 1);

	printf("\nTes nombres après le tri fusion :\n");
	for (i=0; i < num; i++)
		printf("%d ", arr[i]);
	printf("\n");

	return 0;
}
```

Ce code là va te demander combien de nombres tu veux entrer. Ensuite, il va te demander d'entrer tes nombres un par un. À la fin, il va te montrer tes nombres après le tri fusion. 

Fais un tour avec ça et dis-moi ce que tu en penses, cousin. 😏

Je vais te pondre un bout de code qui convertit toutes les majuscules en minuscules avant de faire le tri. Après, on fera un tri simple par ordre alphabétique, en utilisant la valeur ASCII des caractères. Allez, on se lance ! 🚀

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>

#define MAX 1000

void	quick_sort(char *array[], int premier, int dernier)
{
	int		pivot;
	int		i;
	int		j;
	char	*temp;

	if (premier < dernier)
	{
		pivot = premier;
		i = premier;
		j = dernier;

		while (i < j)
		{
			while (strcmp(array[i], array[pivot]) <= 0 && i < dernier)
				i++;
			while (strcmp(array[j], array[pivot]) > 0)
				j--;
			if (i < j)
			{
				temp = array[i];
				array[i] = array[j];
				array[j] = temp;
			}
		}

		temp = array[pivot];
		array[pivot] = array[j];
		array[j] = temp;

		quick_sort(array, premier, j - 1);
		quick_sort(array, j + 1, dernier);
	}
}

void	lower_case(char *array[], int taille)
{
	int i;
	int j;

	for (i = 0; i < taille; i++)
	{
		for (j = 0; array[i][j]; j++)
		{
			array[i][j] = tolower(array[i][j]);
		}
	}
}

int main(void)
{
	char *array[MAX];
	char buf[1024];
	int n = 0;
	int i;

	printf("Entre tes mots, frérot (séparés par un espace) :\n");

	while (scanf("%s", buf) == 1)
	{
		array[n] = strdup(buf);
		n++;
		if (n >= MAX)
			break;
	}

	lower_case(array, n);
	quick_sort(array, 0, n - 1);

	printf("\nTes mots triés :\n");

	for (i = 0; i < n; i++)
		printf("%s ", array[i]);

	printf("\n");

	return 0;
}
```

Fais gaffe, frérot ! Le code que je viens de te montrer utilise la fonction `strdup`, qui est une fonction POSIX, pas une fonction standard du C. Si tu veux compiler ce code avec `gcc`, tu devras peut-être utiliser l'option `-D _POSIX_C_SOURCE=200809L` pour dire à `gcc` que tu veux utiliser les fonctions POSIX.

Et aussi, j'ai fait en sorte que le code convertisse toutes les lettres en minuscules, mais je n'ai pas pris en compte les caractères spéciaux ou les chiffres. Si tu veux aussi prendre en compte ces trucs-là, il faudra un peu modifier le code. Dis-moi si tu veux que je fasse ça. 😉