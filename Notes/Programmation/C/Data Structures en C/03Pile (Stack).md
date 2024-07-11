
Une pile est une structure de données qui fonctionne selon le principe "dernier arrivé, premier sorti" (ou "LIFO", en anglais). C'est comme une pile d'assiettes: la dernière assiette que tu poses sur la pile est la première que tu retires.

Ici, on va créer une pile simple en C. On va définir des fonctions pour ajouter un élément en haut de la pile (`push`), retirer l'élément du haut de la pile (`pop`), et vérifier si la pile est vide (`is_empty`). 

Allons-y, frérot! 👊🏾

```c
#include <stdlib.h>
#include <stdio.h>

typedef struct	s_node
{
	int			data;
	struct s_node	*next;
}				t_node;

t_node	*new_node(int data)
{
	t_node	*node;

	node = malloc(sizeof(t_node));
	if (!node)
		return (NULL);
	node->data = data;
	node->next = NULL;
	return (node);
}

void	push(t_node **top, int data)
{
	t_node	*node;

	node = new_node(data);
	if (!node)
	{
		printf("Erreur d'allocation mémoire, cousin!\n");
		return ;
	}
	node->next = *top;
	*top = node;
}

int	pop(t_node **top)
{
	t_node	*temp;
	int		data;

	if (!*top)
	{
		printf("La pile est vide, frérot!\n");
		return (-1);
	}
	temp = *top;
	*top = (*top)->next;
	data = temp->data;
	free(temp);
	return (data);
}

int	is_empty(t_node *top)
{
	return (!top);
}

int		main(void)
{
	t_node	*stack = NULL;

	push(&stack, 1);
	push(&stack, 2);
	push(&stack, 3);

	while (!is_empty(stack))
	{
		printf("%d\n", pop(&stack));
	}
	
	return (0);
}
```

Ce code crée une pile et y ajoute les nombres 1, 2 et 3. Ensuite, il retire les éléments un par un jusqu'à ce que la pile soit vide.


Les piles sont utilisées dans plein de domaines différents en informatique.

1. **Expression arithmétique et évaluation :** Tu vois les expressions du genre "2 + 2" ou "3 * 5"? Quand tu dois les évaluer, t'utilises une pile. L'ordinateur va pousser les nombres et les opérations dans la pile, puis il va les retirer pour faire le calcul. C'est un truc classique en informatique.

2. **Fonction d'appel :** Quand un programme exécute une fonction, il crée ce qu'on appelle une "frame de pile" qui contient toutes les infos dont la fonction a besoin. Quand la fonction est finie, sa "frame de pile" est retirée (ou "pop"). C'est comme ça que les fonctions savent où reprendre quand elles sont terminées.

3. **Retour en arrière :** Tu sais quand t'es sur un site web, et tu cliques sur le bouton "retour" pour revenir à la page précédente? Eh bien, c'est une pile qui fait ça. Chaque nouvelle page que tu visites est ajoutée à la pile, et quand tu cliques sur "retour", la page du dessus est retirée.

4. **Analyse syntaxique :** Beaucoup de compilateurs utilisent des piles pour vérifier si le code que tu as écrit est bien formé. Ils poussent les caractères un par un dans la pile, et ils les retirent quand ils ont trouvé une instruction complète.

Voilà quelques exemples, mais il y en a plein d'autres. Les piles sont vraiment partout en informatique! 👀


-------------------------------------


La structure de données que je vais te présenter maintenant est la pile (Stack en anglais). Une pile est une structure de données où le dernier élément ajouté est le premier à être supprimé. C'est ce qu'on appelle le principe LIFO (Last In, First Out). C'est comme une pile d'assiettes, frérot. Tu mets une assiette sur le dessus de la pile, et quand tu veux en prendre une, tu prends celle du dessus. 🍽️

Les opérations de base sur une pile sont généralement les suivantes :

- **Push**: Ajouter un élément sur le dessus de la pile.
- **Pop**: Supprimer l'élément du dessus de la pile.
- **Peek/Top**: Consulter l'élément du dessus de la pile sans le supprimer.

Allez, je te montre ça avec du code, cousin. On va créer une petite appli qui va nous permettre d'empiler des nombres entiers et de les dépiler. On pourra aussi consulter le nombre qui est sur le dessus de la pile. On va demander à l'utilisateur les opérations qu'il veut effectuer. 

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

void	push(t_node **top, int data)
{
	t_node	*new;

	new = new_node(data);
	if (!new)
		return ;
	new->next = *top;
	*top = new;
}

int	pop(t_node **top)
{
	t_node	*temp;
	int		data;

	if (!*top)
		return (-1);
	temp = *top;
	data = temp->data;
	*top = (*top)->next;
	free(temp);
	return (data);
}

int	peek(t_node *top)
{
	if (!top)
		return (-1);
	return (top->data);
}

int		main(void)
{
	t_node	*stack = NULL;
	char	command[256];
	int		num;

	while (1)
	{
		printf("\nEnter a command (push [num], pop, peek, quit): ");
		scanf("%s", command);
		if (!strcmp(command, "push"))
		{
			scanf("%d", &num);
			push(&stack, num);
		}
		else if (!strcmp(command, "pop"))
		{
			num = pop(&stack);
			if (num == -1)
				printf("The stack is empty, wesh!\n");
			else
				printf("Popped %d from the stack.\n", num);
		}
		else if (!strcmp(command, "peek"))
		{
			num = peek(stack);
			if (num == -1)
				printf("The stack is empty, frérot!\n");
			else
				printf("Top of the stack is %d.\n", num);
		}
		else if (!strcmp(command, "quit"))
		{
			while (stack)
				pop(&stack);
			break ;
		}
		else
		{
			printf("\nUnknown command, cousin!\n");
			printf("Valid commands are: push [num], pop, peek, quit\n");
		}
	}
	return (0);
}
```

Alors, voilà ce qu'on a là. En premier lieu, on crée notre pile (qui est juste un pointeur vers le dessus de la pile) avec `t_node *stack = NULL;`.

Ensuite, on entre dans une boucle infinie où on demande à l'utilisateur d'entrer une commande. Les commandes possibles sont:

- push num: Pour ajouter un nombre à la pile.
- **pop**: Pour supprimer le nombre au sommet de la pile et l'afficher.
- **peek**: Pour afficher le nombre au sommet de la pile sans le supprimer.
- **quit**: Pour sortir de la boucle et terminer le programme.

La fonction [[strcmp]] est utilisée pour comparer les commandes entrées par l'utilisateur avec les commandes valides. 

C'est tout pour cet exercice, cousin. La structure de données de la pile est utile dans de nombreux scénarios. Par exemple, c'est utilisé dans les navigateurs web pour gérer l'historique des pages visitées. Quand tu cliques sur le bouton "Retour", tu reviens à la dernière page que tu as visitée, c'est-à-dire celle qui est au sommet de la pile. Elle est aussi utilisée dans les éditeurs de texte pour gérer les opérations "Annuler" et "Refaire". Et plein d'autres choses encore. C'est un outil de base de la programmation, frérot! 🚀
