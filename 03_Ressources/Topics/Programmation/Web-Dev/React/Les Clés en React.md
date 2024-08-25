## Les #clés en React permettent de maintenir l'état de chaque élément d'une liste lorsque celle-ci est mise à jour. Elles sont utilisées par React pour identifier de manière unique chaque élément de la #liste et pour s'assurer que chaque élément est associé au bon état ( #state ) lorsque la liste est mise à jour.

##### Voici quelques exemples de ce que les clés permettent de faire dans React :

1.   Mettre à jour une liste de manière efficace lorsque des éléments sont ajoutés, supprimés ou modifiés. Si vous utilisez des clés pour identifier de manière unique chaque élément de la liste, React peut utiliser ces clés pour mettre à jour efficacement la #liste lorsque celle-ci est modifiée.
    
2.  Prévenir les erreurs lorsque des éléments sont ajoutés ou supprimés de la liste. Si vous utilisez des #index comme clés et que vous modifiez la liste en ajoutant ou en supprimant des éléments, les index peuvent changer, ce qui peut entraîner des erreurs. En utilisant des clés uniques, vous pouvez éviter ce problème.
    
3.  Améliorer les #performances de votre application. React utilise les clés pour déterminer quels éléments de la liste ont été modifiés, ajoutés ou supprimés lorsque la liste est mise à jour. Si vous utilisez des clés uniques, React peut effectuer cette opération de manière plus efficace, ce qui peut améliorer les performances de votre application.
    

En résumé, les clés en React sont essentielles pour maintenir l'état de chaque élément d'une liste lorsque celle-ci est mise à jour et pour améliorer les performances de votre application. Il est important de fournir des clés uniques pour chaque élément de la liste lorsque vous utilisez une boucle #map pour générer des composants à partir d'un #tableau de données.

## Voici un exemple qui montre comment utiliser [[useState]] pour gérer une liste de #composants dynamiques en React :

```jsx
import React, { useState } from 'react';

function ListItem(props) {
  return <li>{props.value}</li>;
}

function NumberList() {
  const [numbers, setNumbers] = useState([1, 2, 3, 4, 5]);

  const listItems = numbers.map((number) =>
    <ListItem key={number.toString()} value={number} />
  );
  return (
    <div>
      <ul>{listItems}</ul>
      <button onClick={() => setNumbers([...numbers, numbers.length + 1])}>
        Add number
      </button>
    </div>
  );
}

ReactDOM.render(
  <NumberList />,
  document.getElementById('root')
);
```

Dans cet exemple, le composant `NumberList` utilise `useState` pour gérer un tableau de nombres qui sont affichés dans une liste. Lorsque l'utilisateur clique sur le bouton "Add number", un nouveau nombre est ajouté au tableau et la liste est mise à jour.

Les clés sont utilisées pour identifier de manière unique chaque élément de la liste. Dans ce cas, nous utilisons la valeur de chaque nombre comme clé en la convertissant en chaîne de caractères avec `toString()`. Cela permet à React de maintenir l'état de chaque élément de la liste lorsque celle-ci est mise à jour, en s'assurant que chaque élément est associé au bon état dans le tableau `numbers`.

Vous pouvez essayer de modifier ce code en ajoutant des boutons "Remove number" qui suppriment les éléments du tableau et mettent à jour la liste en conséquence. Assurez-vous d'utiliser des clés uniques pour chaque élément de la liste afin que React puisse mettre à jour efficacement la liste lorsque celle-ci est modifiée.