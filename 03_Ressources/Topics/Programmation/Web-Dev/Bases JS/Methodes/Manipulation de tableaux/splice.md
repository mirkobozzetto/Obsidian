
La méthode `splice()` est une méthode de tableau en JavaScript qui permet de modifier le contenu d'un tableau en supprimant, remplaçant ou ajoutant des éléments à des positions spécifiques. Elle modifie directement le tableau et renvoie les éléments supprimés sous forme d'un nouveau tableau.

Voici comment utiliser la méthode `splice()` :

```javascript
let fruits = ['pomme', 'orange', 'banane', 'raisin'];
let fruitsSupprimes = fruits.splice(1, 2, 'kiwi', 'fraise');

console.log(fruits);
console.log(fruitsSupprimes);
```

Résultat :
```
['pomme', 'kiwi', 'fraise', 'raisin']
['orange', 'banane']
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant quatre éléments : 'pomme', 'orange', 'banane' et 'raisin'. En utilisant `fruits.splice(1, 2, 'kiwi', 'fraise')`, nous supprimons deux éléments à partir de l'index 1 (incluant l'élément à l'index 1) et nous les remplaçons par les éléments 'kiwi' et 'fraise'. La méthode `splice()` modifie le tableau `fruits` en conséquence et renvoie un nouveau tableau contenant les éléments supprimés, qui sont 'orange' et 'banane'.

La méthode `splice()` prend en paramètres l'index de départ, le nombre d'éléments à supprimer et les éléments à ajouter éventuellement. Si vous ne souhaitez pas supprimer d'éléments mais simplement insérer des éléments à une position spécifique, vous pouvez spécifier 0 pour le nombre d'éléments à supprimer.

Il est important de noter que la méthode `splice()` modifie directement le tableau d'origine et renvoie les éléments supprimés sous forme d'un nouveau tableau.