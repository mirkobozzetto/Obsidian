
La méthode `filter()` est une méthode de tableau en JavaScript qui permet de créer un nouveau tableau contenant tous les éléments d'un tableau d'origine qui satisfont à une condition spécifique. Elle ne modifie pas le tableau d'origine.

Voici comment utiliser la méthode `filter()` :

```javascript
let nombres = [1, 2, 3, 4, 5];
let nombresPairs = nombres.filter(nombre => nombre % 2 === 0);

console.log(nombresPairs);
console.log(nombres);
```

Résultat :
```
[2, 4]
[1, 2, 3, 4, 5]
```

Dans cet exemple, nous avons un tableau appelé `nombres` contenant cinq éléments. En utilisant `nombres.filter(nombre => nombre % 2 === 0)`, nous utilisons la méthode `filter()` pour créer un nouveau tableau `nombresPairs` qui contient tous les nombres pairs du tableau d'origine. La condition de filtrage est définie dans la fonction de rappel (callback) fournie à `filter()`. Dans ce cas, seuls les nombres qui satisfont à la condition `nombre % 2 === 0` (nombres pairs) sont inclus dans le nouveau tableau.

Le tableau `nombres` d'origine reste inchangé. La méthode `filter()` renvoie un nouveau tableau contenant les éléments qui satisfont à la condition de filtrage.

La fonction de rappel passée à `filter()` prend en argument chaque élément du tableau et renvoie `true` si l'élément doit être inclus dans le nouveau tableau, ou `false` sinon. Elle permet de définir la condition de filtrage personnalisée en fonction des besoins spécifiques.

Il est important de noter que la méthode `filter()` crée un nouveau tableau avec les éléments filtrés. Si vous souhaitez modifier directement le tableau d'origine en supprimant les éléments qui ne satisfont pas à la condition, vous pouvez utiliser d'autres méthodes de manipulation de tableaux comme [[splice]]() ou une boucle for.