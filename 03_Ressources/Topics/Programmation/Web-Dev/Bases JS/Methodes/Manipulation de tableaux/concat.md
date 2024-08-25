
La méthode `concat()` est une méthode de tableau en JavaScript qui permet de fusionner deux tableaux ou plus en créant un nouveau tableau. Elle ne modifie pas les tableaux d'origine, mais renvoie un nouveau tableau contenant les éléments combinés.

Voici comment utiliser la méthode `concat()` :

```javascript
let fruits1 = ['pomme', 'orange'];
let fruits2 = ['banane', 'raisin'];
let fruitsConcatenes = fruits1.concat(fruits2);

console.log(fruitsConcatenes);
console.log(fruits1);
console.log(fruits2);
```

Résultat :
```
['pomme', 'orange', 'banane', 'raisin']
['pomme', 'orange']
['banane', 'raisin']
```

Dans cet exemple, nous avons deux tableaux, `fruits1` contenant les éléments 'pomme' et 'orange', et `fruits2` contenant les éléments 'banane' et 'raisin'. En utilisant `fruits1.concat(fruits2)`, nous fusionnons les deux tableaux pour créer un nouveau tableau `fruitsConcatenes` qui contient tous les éléments combinés.

Le tableau `fruits1` et le tableau `fruits2` d'origine restent inchangés. La méthode `concat()` renvoie un nouveau tableau contenant les éléments combinés, sans modifier les tableaux d'origine.

La méthode `concat()` peut également accepter des valeurs littérales, pas seulement des tableaux. Par exemple, vous pouvez concaténer un tableau avec des valeurs littérales comme ceci : `fruits1.concat('kiwi', 'fraise')`.

Il est important de noter que la méthode `concat()` crée un nouveau tableau à chaque appel, elle n'agit pas directement sur les tableaux d'origine.