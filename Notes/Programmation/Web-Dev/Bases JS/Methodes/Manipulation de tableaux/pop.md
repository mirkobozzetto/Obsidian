
La méthode `pop()` est une méthode de tableau en JavaScript qui permet de supprimer le dernier élément d'un tableau. Elle modifie directement le tableau en supprimant et renvoyant cet élément.

Voici comment utiliser la méthode `pop()` :

```javascript
let fruits = ['pomme', 'orange', 'banane'];
let dernierFruit = fruits.pop();

console.log(dernierFruit);
console.log(fruits);
```

Résultat :
```
'banane'
['pomme', 'orange']
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant trois éléments : 'pomme', 'orange' et 'banane'. En utilisant `fruits.pop()`, nous supprimons le dernier élément du tableau, qui est 'banane', et le renvoyons dans la variable `dernierFruit`. Après l'appel de `pop()`, le tableau `fruits` est modifié et contient maintenant les deux premiers éléments : 'pomme' et 'orange'.

La méthode `pop()` renvoie l'élément supprimé, ce qui nous permet de le stocker dans une variable pour une utilisation ultérieure si nécessaire.

Il est important de noter que la méthode `pop()` modifie directement le tableau d'origine et renvoie l'élément supprimé. Si vous souhaitez supprimer le premier élément d'un tableau, vous pouvez utiliser la méthode `shift()`. Si vous souhaitez supprimer un élément à une position spécifique dans le tableau, vous pouvez utiliser la méthode `splice()`.