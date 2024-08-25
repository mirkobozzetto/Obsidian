##USER:

La méthode `push()` est une méthode de tableau en JavaScript qui permet d'ajouter un ou plusieurs éléments à la fin d'un tableau existant. Elle modifie directement le tableau en ajoutant les éléments fournis en tant que nouveaux éléments à la fin.

Voici comment utiliser la méthode `push()` :

```javascript
let fruits = ['pomme', 'orange', 'banane'];
fruits.push('raisin', 'fraise');

console.log(fruits);
```

Résultat :
```
['pomme', 'orange', 'banane', 'raisin', 'fraise']
```

Dans cet exemple, nous avons un tableau appelé `fruits` qui contient initialement trois éléments : 'pomme', 'orange' et 'banane'. En utilisant `fruits.push('raisin', 'fraise')`, nous ajoutons les éléments 'raisin' et 'fraise' à la fin du tableau `fruits`. Après l'appel de `push()`, le tableau est modifié et contient les cinq éléments : 'pomme', 'orange', 'banane', 'raisin' et 'fraise'.

La méthode `push()` renvoie la nouvelle longueur du tableau après l'ajout des éléments. Cela peut être utile si vous souhaitez connaître la taille du tableau mise à jour.

Il est important de noter que la méthode `push()` modifie directement le tableau d'origine et ne crée pas de nouveau tableau. Si vous souhaitez ajouter des éléments à un tableau sans le modifier directement, vous pouvez utiliser des méthodes telles que `concat()` ou l'opérateur de propagation (`...`) pour créer une copie du tableau avec les nouveaux éléments ajoutés.