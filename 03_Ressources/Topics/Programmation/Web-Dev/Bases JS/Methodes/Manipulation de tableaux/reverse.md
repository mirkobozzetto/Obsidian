
La méthode `reverse()` est une méthode de tableau en JavaScript qui permet d'inverser l'ordre des éléments d'un tableau. Elle modifie directement le tableau d'origine et ne renvoie rien.

Voici comment utiliser la méthode `reverse()` :

```javascript
let fruits = ['pomme', 'orange', 'banane'];
fruits.reverse();

console.log(fruits);
```

Résultat :
```
['banane', 'orange', 'pomme']
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant trois éléments : 'pomme', 'orange' et 'banane'. En utilisant `fruits.reverse()`, nous utilisons la méthode `reverse()` pour inverser l'ordre des éléments du tableau. Après l'appel de `reverse()`, le tableau `fruits` est modifié et les éléments sont maintenant dans l'ordre inverse : 'banane', 'orange' et 'pomme'.

Il est important de noter que la méthode `reverse()` agit directement sur le tableau d'origine et ne renvoie rien. Elle modifie l'ordre des éléments dans le tableau sans créer de nouveau tableau. Si vous avez besoin d'une copie inversée du tableau sans modifier l'original, vous pouvez utiliser la combinaison de [[slice]]() et [[reverse]](), par exemple : `let fruitsInverse = fruits.slice().reverse();`.

Il est également à noter que la méthode `reverse()` fonctionne mutativement, c'est-à-dire qu'elle modifie le tableau d'origine sans créer une copie distincte.