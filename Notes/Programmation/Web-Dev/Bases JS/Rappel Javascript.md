##  La #destructuration

```jsx
const cat = {
  name: 'Mimi',
  age: 3,
  color: 'white',
};

const { name, age, color } = cat;

const getName = ({ name }) => name;

getName(cat); // 'Mimi'

// On peut l'utiliser comme ça : <Component name={cat.name} age={cat.age} color={cat.color} />
const Component = ({ name, age, color }) => {
  return (
    <div>
      <h1>{name}</h1>
      <p>{age}</p>
      <p>{color}</p>
    </div>
  );
};
```

## Les fonctions fléchés

Ou " #arrow-function" en anglais.

```jsx
const add = (a, b) => a + b;

// Égal à
const add = function (a, b) => {
  return a + b;
}

// Égal à
function add(a, b) {
  return a + b;
}

const Component = ({ numbers }) => {
  return (
    <div>
      {numbers.map(number => <p key={number}>{number}</p>)}
    </div>
  )
}
```

## Les #callback

Les callback ou _méthode de rappel_ en français sont des fonctions passée en paramètre.

```jsx
const getUser = (username, callback) => {
  fetch(`/api/user/${username}`)
    .then((response) => response.json())
    .then((data) => callback(data)); // call callback with data
};

getUser('codelynx', (user) => {
  console.log(user);
});

// React
const Button = ({ onClick }) => {
  <button onClick={onClick}>Click me</button>;
};

const App = () => {
  return <Button onClick={() => console.log('Hello')} />;
};
```

## Les paramètres par défaut

```jsx
const sqrt = (a, n = 2) => {
  return Math.pow(a, n);
};

const showCat = ({ name = 'Kitty' } = {}) => {
  console.log(`Hello cat : ${name}`);
};

const Button = ({ isLoading = false, ...props }) => {
  if (isLoading) return <p>Loading...</p>;
  return <button {...props}>...</button>;
};
```

On peut définir des valeurs par défaut à l'intérieur des objets ou juste pour un paramètre d'une fonction.

## #Import et #export

Bien comprendre la syntaxe d'import et d'export en JavaScript qui permet notamment d'avoir des imports dynamiques et de split son code.

```js
// Date.js
export const dateToString = (date) => {
  return date.toString();
};

// App.js
import { dateToString } from './Date';

console.log(dateToString(new Date()));

// Dynamic import
import React from 'react';

// Importé des composants dynamiques (pas besoin de le savoir avant de faire du React mais tu vas vite l'apprendre.)
const HugeComponent = React.lazy(() => import('./HugeComponent'));
```

## #Ternaire

```jsx
const numbers = 10

const warningText = numbers > 10
  ? "Numbers is upper than 10"
  : "Numbers is lower than 10";

// Égal à

let warningText;
if (numbers > 10) {
  warningText = "Numbers is upper than 10";
} else {
  warningText = "Numbers is lower than 10";
}

const Button = ({ isLoading, children ...props }) => {
  return (
    <button {...props}>
      {isLoading ? "Loading..." : children}
    </button>
  )
}
```

## && et ?? et ||

```js
// Test si la valeur est null ou undefined uniquement
const nullishOperator = (value) => {
  return value ?? 'default';
};

nullishOperator('Test'); // 'Test'
nullishOperator(null); // 'default'
nullishOperator(0); // 0

// Test is la valeur est "falsy"
const orOperator = (value) => {
  return value || 'default';
};

orOperator('Test'); // 'Test'
orOperator(null); // 'default'
orOperator(0); // 'default'

// Inversement test si la valeur est "truthy"
const andOperator = (value) => {
  return value && 'default';
};

andOperator('Test'); // 'default'
andOperator(null); // null
andOperator(0); // 0
```

Le `nullish operator` est utiles pour remplacer un `ternary operator` :

```js
const user = { username: undefined };

// Avant
const username = user.username == null ? user.username : 'default';

// Après
const username = user.username ?? 'default';
```

## Chaîne optionnelle

```jsx
const cat = {
  cat: 'Mimi',
  size: {
    height: 'big',
    width: 'big',
    fullSize: () => {
      return 'very big';
    },
  },
};

// Sans chaîne optionnelle
const height = cat && cat.size && cat.size.height;

// Avec chaîne optionnelle
const height = cat?.size?.height;

// Avec une fonction
const height = cat?.size?.fullSize?.();

const User({ user }) {
  return (
    <div>
      <h1>{user?.name}</h1>
      <p>{user?.age}</p>
    </div>
  )
}
```

## #Promises



C'est un essentiel en JavaScript, en React aussi.

```js
const fakeAsyncCall = () => {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      resolve('Hello world');
    }, 1000);
  });
};

// Sans async/await, la valeur est "Promise"
console.log(fakeAsyncCall());

(async () => {
  // Avec async/await, la valeur est "Hello world" car on attend la valuer
  console.log(await fakeAsyncCall());
})();

// On peut aussi utiliser .then
fakeAsyncCall().then((value) => {
  console.log(value);
});

// Tu peux tester ce code avec ton nom dans ton navigateur
const getAgeForName = (name) => {
  return window
    .fetch(`https://api.agify.io?name=${name}`)
    .then((response) => response.json());
};

getAgeForName('John').then((response) => {
  console.log(response);
});
```

## Le DOM

Le DOM n'est pas lié au JavaScript mais il est lié au web, **React** interagit constamment avec le DOM.

Il faut comprendre ce que c'est, comment ça fonctionne et savoir interagir avec lui !

```html
<div>
  <p>Hello <span id="world">World !</span></p>
</div>

<script>
  const world = document.getElementById('world');
  world.style.color = 'red';
</script>
```

## Conclusion

Si tout ce que je viens de te présenter te rappelle quelque chose, c'est qu'il est temps de plonger dans le magnifique univers de **React** !

Ce framework va te faire avoir une vision magnifique du JavaScript.

Je tiens à te dire que personnellement, j'ai compris énormément de choses en **JavaScript** avec React, car c'est un framework vraiment très proche de ce langage.

Cette article à été créer pour la formation BeginReact.dev !

![](data:image/svg+xml,%3csvg%20xmlns=%27http://www.w3.org/2000/svg%27%20version=%271.1%27%20width=%271512%27%20height=%271460%27/%3e)![logo](https://codelynx.dev/_next/image?url=%2Fimages%2Fbeginreact%2Flogo.png&w=3840&q=75)


BeginReact.dev

Arrête de douter...  
Et viens **dompter** React 🦁 !

[Regarde la vidéo masterclass](https://codelynx.dev/beginreact/get-masterclass)