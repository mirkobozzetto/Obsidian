
La méthode `join()` est une méthode de tableau en JavaScript qui permet de joindre tous les éléments d'un tableau en une seule chaîne de caractères. Elle renvoie cette chaîne de caractères résultante sans modifier le tableau d'origine.

Voici comment utiliser la méthode `join()` :

```javascript
let fruits = ['pomme', 'orange', 'banane'];
let fruitsEnChaine = fruits.join(', ');

console.log(fruitsEnChaine);
console.log(fruits);
```

Résultat :
```
'pomme, orange, banane'
['pomme', 'orange', 'banane']
```

Dans cet exemple, nous avons un tableau appelé `fruits` contenant trois éléments : 'pomme', 'orange' et 'banane'. En utilisant `fruits.join(', ')`, nous utilisons la méthode `join()` pour fusionner tous les éléments du tableau en une seule chaîne de caractères. Les éléments sont séparés par une virgule suivie d'un espace. La méthode `join()` renvoie cette chaîne de caractères résultante.

Le tableau `fruits` d'origine reste inchangé. La méthode `join()` renvoie une chaîne de caractères qui représente les éléments du tableau concaténés selon la séparation spécifiée.

Il est important de noter que la méthode `join()` ne modifie pas le tableau d'origine, elle renvoie simplement une chaîne de caractères résultante. Si vous souhaitez obtenir une représentation sous forme de chaîne de caractères des éléments du tableau sans modifier le tableau d'origine, la méthode `join()` est très pratique.