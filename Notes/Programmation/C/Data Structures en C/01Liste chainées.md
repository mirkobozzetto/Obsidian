
Déjà, t'as besoin d'savoir ce qu'est une structure en C. C'est comme un sac à dos où tu peux mettre plein d'choses dedans, on l'appelle souvent "[[struct]]". 

Dans notre cas, on crée une structure pour représenter un nœud d'une liste chaînée. On l'appelle `t_node` : `t` pour type, et `node` pour nœud. C'est une convention de nommage pour les structures, frère.

```c
typedef struct s_node
{
	int				data;
	struct s_node	*next;
}					t_node;
```

Dans cette struct, on a deux trucs :
- `data` : C'est l'info que le nœud garde. Ici, c'est un nombre entier (`int`), mais ça pourrait être n'importe quoi d'autre.
- `next` : C'est un pointeur vers le nœud suivant dans la chaîne. C'est comme un index pour le prochain mec dans la file.

Maintenant, on veut créer un nouveau nœud. On a besoin d'une fonction pour ça, qu'on appelle `new_node`. On lui donne une valeur `data`, et elle nous donne un nouveau nœud avec cette valeur.

```c
t_node	*new_node(int data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = data;
	new->next = NULL;
	return (new);
}
```

Là, `new` est un pointeur vers une struct `t_node`. On l'alloue avec `malloc`, qui donne de l'espace en mémoire pour cette struct. Si `malloc` foire (genre plus de place en mémoire), il renvoie `NULL`, et on fait pareil. Sinon, on met la valeur `data` dans le nœud, on fait pointer `next` vers `NULL` (pour dire y'a personne après), et on renvoie le nouveau nœud.

Allez, maintenant on va tester notre code dans un programme principal. Pour l'instant, notre code peut être dans un seul fichier, `main.c` par exemple. Plus tard, on pourra le séparer si on a beaucoup de code.

```c
#include <stdlib.h>
#include <stdio.h>

typedef struct s_node
{
	int			data;
	struct s_node	*next;
}					t_node;

t_node	*new_node(int data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = data;
	new->next = NULL;
	return (new);
}

int		main(void)
{
	t_node	*node;

	node = new_node(42);
	if (!node)
	{
		printf("Erreur d'allocation mémoire, cousin!\n");
		return (1);
	}
	printf("Nœud créé avec la valeur : %d\n", node->data);
	free(node);
	return (0);
}
```

Voilà, frérot, ça c'est du code propre. À la fin, on oublie pas de libérer la mémoire qu'on a prise avec [[malloc]], sinon on va finir par en manquer. C'est la règle du jeu, wesh: tout ce qu'on prend avec `malloc`, on le rend avec [[free]]. 👊💥



L'idée maintenant est d'ajouter plus de nœuds à notre liste. On va créer des fonctions pour ajouter un nouveau nœud à la fin de la liste et pour afficher tous les nœuds de la liste. 

Voilà comment on peut le faire :

```c
#include <stdlib.h>
#include <stdio.h>

typedef struct s_node
{
	int			data;
	struct s_node	*next;
}					t_node;

t_node	*new_node(int data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = data;
	new->next = NULL;
	return (new);
}

void add_node(t_node **head, int data)
{
	t_node	*new = new_node(data);
	t_node	*temp = *head;

	if (!*head)
	{
		*head = new;
		return;
	}
	while (temp->next)
		temp = temp->next;
	temp->next = new;
}

void print_list(t_node *node)
{
	while (node)
	{
		printf("%d -> ", node->data);
		node = node->next;
	}
	printf("NULL\n");
}

int		main(void)
{
	t_node	*head = NULL;

	add_node(&head, 42);
	add_node(&head, 23);
	add_node(&head, 17);
	add_node(&head, 66);

	print_list(head);

	// N'oublie pas de libérer la mémoire ici, cousin. Pour l'instant, on le laisse comme ça pour simplifier le code.

	return (0);
}
```

Dans ce code, `add_node` ajoute un nouveau nœud à la fin de la liste, et `print_list` affiche tous les nœuds de la liste. En exécutant le `main`, tu devrais voir s'afficher `42 -> 23 -> 17 -> 66 -> NULL`, ce qui correspond bien à l'ordre dans lequel on a ajouté les nœuds. 💡💪

