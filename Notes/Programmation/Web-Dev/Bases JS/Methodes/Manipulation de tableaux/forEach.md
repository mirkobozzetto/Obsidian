
La méthode `forEach()` est une méthode de tableau en JavaScript qui permet d'itérer sur les éléments d'un tableau et d'exécuter une fonction de rappel pour chaque élément. Elle ne renvoie rien et ne modifie pas le tableau d'origine.

Voici comment utiliser la méthode `forEach()` :

```javascript
let nombres = [1, 2, 3];
nombres.forEach(nombre => {
  console.log(nombre);
});
```

Résultat :
```
1
2
3
```

Dans cet exemple, nous avons un tableau appelé `nombres` contenant trois éléments. En utilisant `nombres.forEach(nombre => { console.log(nombre); })`, nous utilisons la méthode `forEach()` pour itérer sur chaque élément du tableau. La fonction de rappel définie ici prend chaque élément `nombre` et l'affiche dans la console.

La méthode `forEach()` exécute la fonction de rappel pour chaque élément du tableau, dans l'ordre. Elle parcourt tous les éléments du tableau et permet d'effectuer une action spécifique sur chaque élément sans avoir besoin d'écrire une boucle `for` explicite.

Il est important de noter que la méthode `forEach()` ne renvoie rien. Elle est utilisée pour effectuer une action sur chaque élément du tableau, mais elle ne modifie pas le tableau lui-même.

De plus, la méthode `forEach()` ne prend qu'un seul argument, qui est la fonction de rappel. Cette fonction de rappel est appelée pour chaque élément du tableau et peut accepter jusqu'à trois arguments : l'élément actuel, l'index de l'élément et le tableau d'origine. Cependant, seul le premier argument (l'élément actuel) est généralement utilisé.

Notez également que si vous souhaitez modifier directement les éléments du tableau, vous pouvez utiliser d'autres méthodes telles que [[map]]() ou [[reduce]]().