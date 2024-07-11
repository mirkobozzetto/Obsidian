Tag:  #daily #javascript 


afin d'acceder au valeurs grace au #destructuring 
on peut utiliser ce genre de notation, et c'est notamment très utilisé dans la création de #Hooks avec #React 

```js
let arr = ["John", "Smith"]
let [firstName, surname] = arr;
alert(firstName); // John
alert(surname);  // Smith
```

Le côté gauche [firstName, surname] définit le **modèle de destructuration** - il indique que le premier élément du tableau doit être assigné à la variable firstName, et le deuxième élément doit être assigné à la variable surname.
  

Le côté droit arr est l'objet à décomposer. Lorsque le code est exécuté, les valeurs "John" et "Smith" sont extraites du tableau arr et assignées respectivement aux variables firstName et surname.
```js
let user = {};
[user.name, user.surname] = "John Smith".split(' ');

alert(user.name); // John
alert(user.surname); // Smith
```


1. "John Smith".split(' ') divise la chaîne de caractères en un tableau de deux éléments : ["John", "Smith"].

1. [user.name, user.surname] = ... affecte le premier élément du tableau (soit "John") à user.name et le deuxième élément (soit "Smith") à user.surname.

```js
let [name1, name2, ...rest] = ["Julius", "Caesar", "Consul", "of the Roman Republic"];

// rest is an array of items, starting from the 3rd one
alert(rest[0]); // Consul
alert(rest[1]); // of the Roman Republic
alert(rest.length); // 2

```

- `rest[0]` affiche "Consul", qui est le premier élément du tableau rest.

- `rest[1]` affiche "of the Roman Republic", qui est le deuxième élément du tableau rest.

- `rest.length` affiche 2, qui est le nombre d'éléments dans le tableau rest.
  

Donc, la destructuration de tableau permet de séparer les éléments d'un tableau dans différentes variables, en laissant le reste des éléments dans un nouveau tableau.

___

 La destructuration est très utile en React, notamment avec les hooks.
  

Par exemple, avec le hook #useState, on peut utiliser la destructuration pour récupérer facilement la valeur et la fonction de mise à jour :

  

```jsx
 const [count, setCount] = useState(0); 
```

  

Ici, count contiendra la valeur de l'état, et setCount sera la fonction pour mettre à jour cet état.

  D'ailleurs en parlant de ça il serait intéressant d'aller lire cet article sur le #state en react

[Preserving and Resetting State – React](https://react.dev/learn/preserving-and-resetting-state)

React construit des arbres de rendu pour la structure de composants dans votre interface utilisateur. Lorsque vous donnez un état à un composant, vous pourriez penser que l'état "vit" à l'intérieur du composant. Mais en réalité, l'état est détenu à l'intérieur de React. 

React associe chaque morceau d'état qu'il détient au bon composant en fonction de la position de ce composant dans l'arbre de rendu.


```jsx
import { useState } from 'react';

export default function App() {
  const counter = <Counter />;
  return (
    <div>
      {counter}
      {counter}
    </div>
  );
}

function Counter() {
  const [score, setScore] = useState(0);
  const [hover, setHover] = useState(false);

  let className = 'counter';
  if (hover) {
    className += ' hover';
  }

  return (
    <div
      className={className}
      onPointerEnter={() => setHover(true)}
      onPointerLeave={() => setHover(false)}
    >
      <h1>{score}</h1>
      <button onClick={() => setScore(score + 1)}>
        Add one
      </button>
    </div>
  );
}

```

Dans cet exemple, il n'y a qu'une seule balise JSX <Counter />, mais elle est rendue à deux positions différentes dans l'arbre de rendu de React.

Bien que le même composant <Counter /> soit utilisé, React considère qu'il s'agit de deux instances distinctes, car elles sont rendues à deux positions différentes dans l'arbre de rendu.

Donc, le **state est lié à la position dans l'arbre de rendu**, et non au composant lui-même. React gère cela en interne pour s'assurer que chaque composant a son propre état isolé.
___
- Dans React, chaque composant à l'écran a un état complètement isolé.

- Lorsque vous rendez deux composants Counter côte à côte, chacun d'eux obtient son propre état score et hover indépendant.

- Lorsque vous cliquez sur les deux compteurs, ils n'affectent pas l'un l'autre, car leurs états sont complètement séparés.

  

Cela est dû au fait que React associe chaque morceau d'état qu'il détient avec le bon composant en fonction de sa position dans l'arbre de rendu. Même si vous avez seulement un seul élément <Counter /> dans votre JSX, React le rend à deux positions différentes dans l'arbre, ce qui crée deux instances de Counter avec des états indépendants.

  

React préserve l'état de chaque composant en fonction de sa position dans l'arbre de rendu, ce qui permet d'avoir des composants complètement indépendants les uns des autres.

```jsx
import { useState } from 'react';

export default function App() {
  return (
    <div>
      <Counter />
      <Counter />
    </div>
  );
}

function Counter() {
  const [score, setScore] = useState(0);
  const [hover, setHover] = useState(false);

  let className = 'counter';
  if (hover) {
    className += ' hover';
  }

  return (
    <div
      className={className}
      onPointerEnter={() => setHover(true)}
      onPointerLeave={() => setHover(false)}
    >
      <h1>{score}</h1>
      <button onClick={() => setScore(score + 1)}>
        Add one
      </button>
    </div>
  );
}

```

___
React conserve l'état tant que le même composant est rendu à la même position dans l'arbre.

L'état n'est pas lié aux balises JSX, mais à la position de l'arbre où le JSX est placé.

Vous pouvez forcer la réinitialisation de l'état d'un sous-arbre en lui donnant une clé différente.

Ne pas imbriquer les définitions de composants, sinon vous risquez de réinitialiser l'état par accident,

la position dans l'arbre de rendu est essentielle pour la gestion de l'état dans React. Vous pouvez contrôler la préservation ou la réinitialisation de l'état en jouant sur la structure de l'arbre et l'utilisation de clés.

Imaginons une application de tableau de bord avec deux compteurs, l'un pour Taylor et l'autre pour Sarah. Lorsque l'on change de joueur, on veut que le compteur soit réinitialisé, car il s'agit de deux compteurs indépendants.

```jsx
export default function Scoreboard() {
  const [isPlayerA, setIsPlayerA] = useState(true);

  return (
    <div>
      {isPlayerA ? (
        <Counter key="Taylor" person="Taylor" />
      ) : (
        <Counter key="Sarah" person="Sarah" />
      )}
      <button onClick={() => setIsPlayerA(!isPlayerA)}>
        Next player!
      </button>
    </div>
  );
}

function Counter({ person }) {
  const [score, setScore] = useState(0);
  // ...
}

```