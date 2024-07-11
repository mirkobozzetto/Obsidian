
La méthode `shift()` est une méthode de tableau en JavaScript qui permet de supprimer le premier élément d'un tableau. Elle modifie directement le tableau en supprimant et renvoyant cet élément.

Voici comment utiliser la méthode `shift()` :

```javascript
let fruits = ['pomme', 'orange', 'banane'];
let premierFruit = fruits.shift();

console.log(premierFruit);
console.log(fruits);
```

Résultat :
```
'pomme'
['orange', 'banane']
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant trois éléments : 'pomme', 'orange' et 'banane'. En utilisant `fruits.shift()`, nous supprimons le premier élément du tableau, qui est 'pomme', et le renvoyons dans la variable `premierFruit`. Après l'appel de `shift()`, le tableau `fruits` est modifié et contient maintenant les deux derniers éléments : 'orange' et 'banane'.

La méthode `shift()` renvoie l'élément supprimé, ce qui nous permet de le stocker dans une variable pour une utilisation ultérieure si nécessaire.

Il est important de noter que la méthode `shift()` modifie directement le tableau d'origine et renvoie l'élément supprimé. Si vous souhaitez supprimer le dernier élément d'un tableau, vous pouvez utiliser la méthode [[pop]](). Si vous souhaitez supprimer des éléments à une position spécifique dans le tableau, vous pouvez utiliser la méthode [[splice]]().