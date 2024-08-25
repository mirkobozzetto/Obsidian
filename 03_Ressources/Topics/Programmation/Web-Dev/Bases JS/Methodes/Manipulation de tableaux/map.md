
La méthode `map()` est une méthode de tableau en JavaScript qui permet de créer un nouveau tableau en appliquant une transformation à chaque élément du tableau d'origine. Elle ne modifie pas le tableau d'origine.

Voici comment utiliser la méthode `map()` :

```javascript
let nombres = [1, 2, 3, 4, 5];
let carres = nombres.map(nombre => nombre * nombre);

console.log(carres);
console.log(nombres);
```

Résultat :
```
[1, 4, 9, 16, 25]
[1, 2, 3, 4, 5]
```

Dans cet exemple, nous avons un tableau appelé `nombres` contenant cinq éléments. En utilisant `nombres.map(nombre => nombre * nombre)`, nous utilisons la méthode `map()` pour créer un nouveau tableau `carres` qui contient les carrés de chaque nombre du tableau d'origine. La transformation est définie dans la fonction de rappel (callback) fournie à `map()`. Dans ce cas, chaque élément du tableau `nombres` est multiplié par lui-même pour obtenir le carré correspondant.

Le tableau `nombres` d'origine reste inchangé. La méthode `map()` renvoie un nouveau tableau contenant les éléments transformés.

La fonction de rappel passée à `map()` prend en argument chaque élément du tableau et renvoie la valeur transformée correspondante. Elle permet de définir la logique de transformation personnalisée en fonction des besoins spécifiques.

Il est important de noter que la méthode `map()` crée un nouveau tableau avec les éléments transformés. Si vous souhaitez modifier directement le tableau d'origine en remplaçant ses éléments par les éléments transformés, vous pouvez utiliser une boucle for ou d'autres méthodes de manipulation de tableaux comme [[forEach]]().