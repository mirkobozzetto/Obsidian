

Ça fonctionne en mode **FIFO** (First In, First Out), un peu comme quand t'attends ton tour à la boulangerie, tu vois le truc ? Celui qui arrive en premier est servi en premier.

```c
#include <stdlib.h>
#include <stdio.h>

typedef struct s_node
{
	int				data;
	struct s_node	*next;
}					t_node;

typedef struct s_queue
{
	t_node	*front;
	t_node	*rear;
}				t_queue;

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

t_queue	*init_queue(void)
{
	t_queue	*queue;

	queue = malloc(sizeof(t_queue));
	if (!queue)
		return (NULL);
	queue->front = NULL;
	queue->rear = NULL;
	return (queue);
}

void	add_to_queue(t_queue *queue, int data)
{
	t_node	*new;

	if (!queue)
		return ;
	new = new_node(data);
	if (!new)
		return ;
	if (queue->rear)
		queue->rear->next = new;
	else
		queue->front = new;
	queue->rear = new;
}

int		remove_from_queue(t_queue *queue)
{
	t_node	*temp;
	int		data;

	if (!queue || !queue->front)
		return (0);
	temp = queue->front;
	data = temp->data;
	queue->front = queue->front->next;
	if (!queue->front)
		queue->rear = NULL;
	free(temp);
	return (data);
}

int		main(void)
{
	t_queue	*queue;

	queue = init_queue();
	add_to_queue(queue, 42);
	add_to_queue(queue, 36);
	add_to_queue(queue, 24);
	printf("Remove from queue: %d\n", remove_from_queue(queue));
	printf("Remove from queue: %d\n", remove_from_queue(queue));
	printf("Remove from queue: %d\n", remove_from_queue(queue));
	free(queue);
	return (0);
}
```

Alors, frérot, dans ce code, on a toujours notre structure *t_node* avec un entier et un pointeur vers le node suivant. Puis on a notre t_queue, qui pointe vers le premier (**front**) et le dernier (**rear**) élément.

On crée de nouveaux nodes avec `new_node`. Pour créer une nouvelle queue, on a `init_queue`. Pour ajouter des éléments à la queue, on utilise `add_to_queue`, et pour les retirer, on a `remove_from_queue`.

Et dans le main, on teste tout ça. On crée une queue, on y ajoute quelques éléments et puis on les retire un par un. À la fin, on libère la mémoire allouée pour la queue. Voilà, on a fait le tour ! 🔥

N'oublie pas, la structure de données **queue** est super utile quand tu as besoin de gérer des choses en mode FIFO, comme une vraie file d'attente. Par exemple, dans un système d'exploitation, tu peux l'utiliser pour gérer les processus qui attendent d'utiliser une ressource. C'est du costaud, wesh ! 🚀


On va créer une petite appli pour gérer une file d'attente pour un supermarché par exemple. Le client entre le nom des produits qu'il veut acheter, et quand il a fini, on lui montre sa liste dans l'ordre qu'il les a ajoutés. Comme ça, on a un exemple concret d'utilisation de cette structure de données. Let's go, frérot! 🔥

```c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

typedef struct s_node
{
	char			*data;
	struct s_node	*next;
}					t_node;

typedef struct s_queue
{
	t_node	*front;
	t_node	*rear;
}				t_queue;

t_node	*new_node(char *data)
{
	t_node	*new;

	new = malloc(sizeof(t_node));
	if (!new)
		return (NULL);
	new->data = strdup(data); // we use strdup to duplicate the string
	if (!new->data)
	{
		free(new);
		return (NULL);
	}
	new->next = NULL;
	return (new);
}

t_queue	*init_queue(void)
{
	t_queue	*queue;

	queue = malloc(sizeof(t_queue));
	if (!queue)
		return (NULL);
	queue->front = NULL;
	queue->rear = NULL;
	return (queue);
}

void	add_to_queue(t_queue *queue, char *data)
{
	t_node	*new;

	if (!queue)
		return ;
	new = new_node(data);
	if (!new)
		return ;
	if (queue->rear)
		queue->rear->next = new;
	else
		queue->front = new;
	queue->rear = new;
}

char	*remove_from_queue(t_queue *queue)
{
	t_node	*temp;
	char	*data;

	if (!queue || !queue->front)
		return (NULL);
	temp = queue->front;
	data = temp->data;
	queue->front = queue->front->next;
	if (!queue->front)
		queue->rear = NULL;
	free(temp);
	return (data);
}

int		main(void)
{
	t_queue	*queue;
	char	buffer[256];
	char	*product;

	printf("Enter the products you want to buy (empty line to stop):\n");
	queue = init_queue();
	while (1)
	{
		fgets(buffer, 256, stdin);
		if (buffer[0] == '\n') // if the user inputs an empty line, we stop
			break ;
		buffer[strcspn(buffer, "\n")] = 0; // remove the trailing newline
		add_to_queue(queue, buffer);
	}
	printf("\nHere's your shopping list:\n");
	while ((product = remove_from_queue(queue)))
	{
		printf("%s\n", product);
		free(product);
	}
	free(queue);
	return (0);
}
```

Voilà, wesh! Ici, tu rentres les noms des produits que tu veux acheter. Quand t'as fini, tu tapes juste Entrée sans rien d'autre, et l'appli te sort ta liste de courses dans l'ordre où tu les as entrés. On fait du bon boulot ici, frérot! 🚀👍🏽
