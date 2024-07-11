
La méthode `slice()` est une méthode de tableau en JavaScript qui permet de créer une copie superficielle (shallow copy) d'une portion spécifique d'un tableau existant. Elle renvoie un nouveau tableau contenant les éléments sélectionnés, sans modifier le tableau d'origine.

Voici comment utiliser la méthode `slice()` :

```javascript
let fruits = ['pomme', 'orange', 'banane', 'raisin'];
let fruitsCopie = fruits.slice(1, 3);

console.log(fruitsCopie);
console.log(fruits);
```

Résultat :
```
['orange', 'banane']
['pomme', 'orange', 'banane', 'raisin']
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant quatre éléments : 'pomme', 'orange', 'banane' et 'raisin'. En utilisant `fruits.slice(1, 3)`, nous extrayons une portion du tableau à partir de l'index 1 jusqu'à l'index 2 (non inclus). La méthode `slice()` renvoie un nouveau tableau contenant les éléments sélectionnés, dans cet cas-ci 'orange' et 'banane'.

Le tableau `fruits` d'origine reste inchangé. Cela permet de créer une copie d'une partie spécifique d'un tableau sans altérer l'original.

La méthode `slice()` peut prendre deux paramètres optionnels : l'index de début (inclus) et l'index de fin (non inclus). Si aucun paramètre n'est spécifié, `slice()` renverra une copie complète du tableau.

Il est important de noter que la méthode `slice()` crée une copie superficielle du tableau, ce qui signifie que si les éléments du tableau sont des objets ou des tableaux, ils seront partagés par référence entre l'original et la copie.