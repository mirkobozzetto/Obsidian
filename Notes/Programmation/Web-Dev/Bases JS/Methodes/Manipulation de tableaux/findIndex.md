
La méthode `findIndex()` est une méthode de tableau en JavaScript qui permet de trouver l'index du premier élément dans le tableau qui satisfait à une condition donnée. Elle renvoie cet index s'il est trouvé, sinon elle renvoie -1.

Voici comment utiliser la méthode `findIndex()` :

```javascript
let nombres = [1, 2, 3, 4, 5];
let indexPair = nombres.findIndex(nombre => nombre % 2 === 0);
let indexSuperieurA10 = nombres.findIndex(nombre => nombre > 10);

console.log(indexPair);
console.log(indexSuperieurA10);
```

Résultat :
```
1
-1
```

Dans cet exemple, nous avons un tableau appelé `nombres` contenant cinq éléments. En utilisant `nombres.findIndex(nombre => nombre % 2 === 0)`, nous utilisons la méthode `findIndex()` pour trouver l'index du premier nombre pair dans le tableau. La méthode `findIndex()` renvoie 1 car 2 est le premier nombre pair rencontré, et son index est 1.

Dans le deuxième exemple, nous utilisons `nombres.findIndex(nombre => nombre > 10)` pour trouver l'index du premier nombre supérieur à 10 dans le tableau. La méthode `findIndex()` renvoie -1 car aucun des nombres du tableau ne satisfait à cette condition.

La méthode `findIndex()` itère sur chaque élément du tableau, en évaluant la condition spécifiée dans la fonction de rappel pour chaque élément. Elle renvoie l'index du premier élément qui satisfait à la condition, sinon elle renvoie -1 si aucun élément ne satisfait à la condition.

Il est important de noter que la méthode `findIndex()` s'arrête dès qu'un élément satisfait à la condition et ne parcourt pas les éléments restants du tableau. Elle renvoie l'index du premier élément trouvé qui satisfait à la condition de recherche.