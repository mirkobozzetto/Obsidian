
La méthode `lastIndexOf()` est une méthode de tableau en JavaScript qui permet de trouver le dernier index auquel un élément donné peut être trouvé dans le tableau. Elle recherche l'élément en partant de la fin du tableau et renvoie l'index de l'élément recherché, ou -1 si l'élément n'est pas présent dans le tableau.

Voici comment utiliser la méthode `lastIndexOf()` :

```javascript
let fruits = ['pomme', 'orange', 'banane', 'orange'];
let lastIndexOrange = fruits.lastIndexOf('orange');
let lastIndexFraise = fruits.lastIndexOf('fraise');

console.log(lastIndexOrange);
console.log(lastIndexFraise);
```

Résultat :
```
3
-1
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant quatre éléments : 'pomme', 'orange', 'banane' et 'orange'. En utilisant `fruits.lastIndexOf('orange')`, nous recherchons le dernier index de l'élément 'orange' dans le tableau. La méthode `lastIndexOf()` renvoie l'index 3, car la dernière occurrence de 'orange' se trouve à cet index dans le tableau.

Si l'élément recherché n'est pas présent dans le tableau, la méthode `lastIndexOf()` renverra -1. C'est le cas lorsque nous recherchons l'index de l'élément 'fraise', qui n'est pas présent dans le tableau `fruits`.

Il est important de noter que la méthode `lastIndexOf()` effectue une recherche en partant de la fin du tableau. Si vous souhaitez rechercher toutes les occurrences d'un élément dans le tableau, vous pouvez utiliser une boucle ou des méthodes telles que [[filter]]() ou [[reduce]]().