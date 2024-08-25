
La méthode `indexOf()` est une méthode de tableau en JavaScript qui permet de trouver le premier index auquel un élément donné peut être trouvé dans le tableau. Elle renvoie l'index de l'élément recherché, ou -1 si l'élément n'est pas présent dans le tableau.

Voici comment utiliser la méthode `indexOf()` :

```javascript
let fruits = ['pomme', 'orange', 'banane'];
let indexOrange = fruits.indexOf('orange');
let indexFraise = fruits.indexOf('fraise');

console.log(indexOrange);
console.log(indexFraise);
```

Résultat :
```
1
-1
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant trois éléments : 'pomme', 'orange' et 'banane'. En utilisant `fruits.indexOf('orange')`, nous recherchons l'index de l'élément 'orange' dans le tableau. La méthode `indexOf()` renvoie l'index 1, car 'orange' se trouve à cet index dans le tableau.

Si l'élément recherché n'est pas présent dans le tableau, la méthode `indexOf()` renverra -1. C'est le cas lorsque nous recherchons l'index de l'élément 'fraise', qui n'est pas présent dans le tableau `fruits`.

Il est important de noter que la méthode `indexOf()` recherche l'élément en utilisant une comparaison stricte (vérification de la valeur et du type). Si vous souhaitez effectuer une recherche basée sur une condition plus complexe, vous pouvez utiliser des méthodes telles que `find()` ou `findIndex()`.