C'est un type de structure de données très important et répandu. On peut l'utiliser pour représenter une hiérarchie (comme une structure d'entreprise), pour stocker des données de manière à pouvoir les récupérer rapidement (comme dans une base de données indexée), pour analyser des expressions mathématiques, et bien plus encore.

Un arbre binaire est constitué de nœuds, chaque nœud ayant zéro, un ou deux enfants. Dans une représentation graphique, chaque nœud est dessiné au-dessus de ses enfants. Il y a un nœud spécial appelé la "racine" qui n'a pas de parent.

Voici une implémentation basique en C d'un arbre binaire :

```c
#include <stdlib.h>
#include <stdio.h>

typedef struct		s_node
{
	int				data;
	struct s_node	*left;
	struct s_node	*right;
}					t_node;

t_node	*create_node(int data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = data;
	new->left = NULL;
	new->right = NULL;
	return (new);
}
```

Avec cette structure, on peut créer des nœuds avec une valeur de données, un lien vers le nœud enfant gauche et un lien vers le nœud enfant droit. La fonction `create_node` crée un nouveau nœud avec la valeur de données spécifiée et des liens enfants initialement définis sur NULL.

Voici une façon simple de créer un arbre binaire à partir de valeurs entrées par l'utilisateur. Notez que cet exemple est assez simple et n'implique pas l'équilibrage de l'arbre ou l'ajout de nœuds dans un ordre particulier.

```c
#include <stdlib.h>
#include <stdio.h>

typedef struct		s_node
{
	int				data;
	struct s_node	*left;
	struct s_node	*right;
}					t_node;

t_node	*create_node(int data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = data;
	new->left = NULL;
	new->right = NULL;
	return (new);
}

int	main(void)
{
	t_node	*root;
	int		val;

	printf("Entrez la valeur pour la racine de l'arbre: ");
	scanf("%d", &val);
	root = create_node(val);
	root->left = create_node(2);
	root->right = create_node(3);
	root->left->left = create_node(4);
	root->left->right = create_node(5);
	printf("L'arbre a été créé. La racine est %d.\n", root->data);
	return (0);
}
```
Dans ce programme, l'utilisateur est invité à entrer une valeur pour la racine de l'arbre. Les autres nœuds sont ajoutés manuellement dans le code. Lors de l'exécution du programme, l'utilisateur verra un message indiquant que l'arbre a été créé et affichant la valeur de la racine.

Il convient de noter que cet exemple est assez basique. En pratique, vous voudriez probablement ajouter plus de fonctionnalités, comme une fonction pour ajouter des nœuds à l'arbre de manière ordonnée, une fonction pour rechercher une valeur dans l'arbre, une fonction pour supprimer un nœud de l'arbre, etc..

Essayons une structure de données appelée "Arbre Binaire de Recherche" (Binary Search Tree - BST en anglais). 

Un BST est un type d'arbre binaire où chaque nœud a une valeur supérieure à tous les nœuds de son sous-arbre gauche, et une valeur inférieure ou égale à tous les nœuds de son sous-arbre droit.

Voici un exemple de code qui crée un BST et qui ajoute des nœuds à l'arbre de manière ordonnée. Ensuite, il imprime toutes les valeurs de l'arbre en utilisant un parcours "inorder" (gauche, racine, droite), qui affiche les valeurs dans l'ordre croissant.

```c
#include <stdio.h>
#include <stdlib.h>

typedef struct		s_node
{
	int				data;
	struct s_node	*left;
	struct s_node	*right;
}					t_node;

t_node	*create_node(int data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = data;
	new->left = NULL;
	new->right = NULL;
	return (new);
}

t_node	*insert_node(t_node *root, int data)
{
	if (root == NULL)
		return create_node(data);
	if (data < root->data)
		root->left = insert_node(root->left, data);
	else
		root->right = insert_node(root->right, data);
	return root;
}

void	inorder_traversal(t_node *root)
{
	if (root != NULL)
	{
		inorder_traversal(root->left);
		printf("%d \n", root->data);
		inorder_traversal(root->right);
	}
}

int	main(void)
{
	t_node	*root = NULL;
	int		val;

	printf("Entrez la valeur pour la racine de l'arbre: ");
	scanf("%d", &val);
	root = insert_node(root, val);
	root = insert_node(root, 2);
	root = insert_node(root, 3);
	root = insert_node(root, 1);
	root = insert_node(root, 5);
	printf("Arbre créé. Les valeurs dans l'ordre croissant sont:\n");
	inorder_traversal(root);
	return (0);
}
```

Ce code crée un BST, ajoute quelques valeurs, puis imprime ces valeurs en ordre croissant. Vous pouvez ajouter plus de valeurs pour voir comment elles sont ajoutées à l'arbre de manière ordonnée et comment elles sont affichées en ordre croissant lors de l'utilisation du parcours "inorder".

Supposons que nous avons les numéros 4, 2, 8, 5, 10 et 1 à insérer dans l'arbre, dans cet ordre.

1.  On commence par insérer 4. C'est notre nœud racine.

    ```
    4
    ```

2.  Ensuite, on insère 2. Comme 2 est inférieur à 4, il devient un nœud enfant à gauche.

    ```
      4
     /
    2
    ```

3.  On insère ensuite 8. Comme 8 est supérieur à 4, il devient un nœud enfant à droite.

    ```
      4
     / \
    2   8
    ```

4.  Ensuite, on insère 5. Comme 5 est inférieur à 8 mais supérieur à 4, il devient un nœud enfant à gauche de 8.

    ```
      4
     / \
    2   8
       /
      5
    ```

5.  On insère ensuite 10. Comme 10 est supérieur à 8, il devient un nœud enfant à droite de 8.

    ```
      4
     / \
    2   8
       / \
      5   10
    ```

6.  Enfin, on insère 1. Comme 1 est inférieur à 2 qui est lui-même inférieur à 4, il devient un nœud enfant à gauche de 2.

    ```
        4
       / \
      2   8
     /   / \
    1   5   10
    ```

Donc, si on fait un parcours inorder (gauche, racine, droite), on obtient les numéros dans l'ordre croissant : 1, 2, 4, 5, 8, 10. Voilà un exemple de la manière dont un arbre binaire de recherche organise ses données.


Les arbres binaires de recherche sont très utiles dans de nombreux domaines :

1. **Base de données**: Les arbres binaires de recherche sont souvent utilisés dans les bases de données pour faciliter la recherche rapide d'informations. Par exemple, si tu as une base de données avec des millions d'utilisateurs et que tu veux trouver rapidement les informations d'un utilisateur spécifique, un arbre binaire de recherche peut être un bon choix.

2. **Index de fichiers**: Les systèmes de fichiers sur ton ordinateur utilisent également des arbres binaires de recherche pour indexer les fichiers, ce qui facilite la recherche et l'organisation des fichiers.

3. **Compilation de code**: Les compilateurs utilisent souvent des arbres binaires de recherche pour chercher rapidement dans les tables de symboles lors de la compilation du code.

4. **Jeux**: Dans les jeux et les algorithmes de recherche de chemin, les arbres binaires de recherche peuvent être utilisés pour stocker les positions possibles ou les mouvements d'un personnage.

En général, chaque fois que tu as besoin d'effectuer une recherche rapide sur un grand ensemble de données, un arbre binaire de recherche peut être une bonne option.
