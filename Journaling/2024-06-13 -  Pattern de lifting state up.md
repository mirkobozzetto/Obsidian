# Pattern de lifting state up en React

#react #liftingstateup #state  #composants #props


Le pattern de "lifting state up" (ou "remontée d'état") est un concept clé dans le développement d'applications React. Il consiste à déplacer l'état partagé entre plusieurs composants vers leur ancêtre commun le plus proche. Cela permet une meilleure gestion de l'état et une synchronisation plus facile des données entre les composants.

## Pourquoi utiliser le pattern de lifting state up ?

Lorsque plusieurs composants ont besoin d'accéder ou de modifier les mêmes données, il est préférable de stocker ces données dans leur ancêtre commun. Cela présente plusieurs avantages :

- Évite la duplication de l'état dans plusieurs composants
- Facilite la synchronisation des données entre les composants
- Rend le code plus maintenable et moins sujet aux erreurs

## Comment mettre en place le pattern de lifting state up ?

Pour mettre en place ce pattern, suivez ces étapes :

1. Identifiez les composants qui partagent le même état.
2. Trouvez leur ancêtre commun le plus proche.
3. Déplacez l'état partagé vers cet ancêtre commun.
4. Passez l'état et les fonctions de modification de l'état en tant que props aux composants enfants qui en ont besoin.

## Exemple de mise en œuvre

Prenons l'exemple d'un formulaire de conversion de température composé de deux champs : un pour la température en Celsius et un autre pour la température en Fahrenheit. Les deux champs doivent être synchronisés, de sorte que lorsqu'on modifie l'un, l'autre se met à jour automatiquement.

```jsx
function TemperatureInput(props) {
  function handleChange(e) {
    props.onTemperatureChange(e.target.value);
  }

  return (
    <fieldset>
      <legend>Entrez la température en {props.scale} :</legend>
      <input value={props.temperature} onChange={handleChange} />
    </fieldset>
  );
}
```

Dans ce cas, l'état (la température) et la fonction de modification de l'état (`onTemperatureChange`) sont passés en tant que props depuis le composant parent.

```jsx
function Calculator(props) {
  const [temperature, setTemperature] = useState('');
  const [scale, setScale] = useState('c');

  function handleCelsiusChange(temperature) {
    setScale('c');
    setTemperature(temperature);
  }

  function handleFahrenheitChange(temperature) {
    setScale('f');
    setTemperature(temperature);
  }

  function toCelsius(fahrenheit) {
    return (fahrenheit - 32) * 5 / 9;
  }

  function toFahrenheit(celsius) {
    return (celsius * 9 / 5) + 32;
  }

  const celsius = scale === 'f' ? toCelsius(temperature) : temperature;
  const fahrenheit = scale === 'c' ? toFahrenheit(temperature) : temperature;

  return (
    <div>
      <TemperatureInput
        scale="c"
        temperature={celsius}
        onTemperatureChange={handleCelsiusChange} />
      <TemperatureInput
        scale="f"
        temperature={fahrenheit}
        onTemperatureChange={handleFahrenheitChange} />
    </div>
  );
}
```

Dans cet exemple, l'état (température et échelle) est stocké dans le composant `Calculator`, qui est l'ancêtre commun des deux composants `TemperatureInput`. Les fonctions de modification de l'état (`handleCelsiusChange` et `handleFahrenheitChange`) sont également définies dans `Calculator` et passées en tant que props aux composants enfants.

___

#propsdrilling 
Le "props drilling"est un problème courant dans les applications React où les props sont passées à travers plusieurs niveaux de composants intermédiaires qui n'ont pas nécessairement besoin de ces props, uniquement dans le but de les transmettre à des composants enfants plus profonds dans l'arborescence.

Voici un exemple pour illustrer le concept :

```jsx
const GrandParent = () => {
  const data = "Hello, World!";
  return <Parent data={data} />;
};

const Parent = ({ data }) => {
  return <Child data={data} />;
};

const Child = ({ data }) => {
  return <GrandChild data={data} />;
};

const GrandChild = ({ data }) => {
  return <p>{data}</p>;
};
```

Dans cet exemple, la prop `data` est passée du composant `GrandParent` au composant `GrandChild` en traversant les composants `Parent` et `Child`, même si ces derniers n'utilisent pas directement cette prop. C'est ce qu'on appelle le "prop drilling".

Problèmes liés au prop drilling :
1. Lisibilité réduite : Le passage de props à travers de nombreux niveaux de composants peut rendre le code moins lisible et plus difficile à comprendre.
2. Maintenance difficile : Si vous devez apporter des modifications aux props, vous devez mettre à jour tous les composants intermédiaires, ce qui peut être fastidieux et sujet aux erreurs.
3. Réutilisabilité réduite : Les composants intermédiaires deviennent moins réutilisables car ils dépendent de props spécifiques qui ne leur sont pas destinées.

Solutions au prop drilling :
1. Composition de composants : Au lieu de passer les props à travers plusieurs niveaux, vous pouvez utiliser la composition de composants pour passer directement les données aux composants qui en ont besoin.
2. Contexte (Context) : Le contexte React permet de partager des données entre des composants sans avoir à passer explicitement les props à chaque niveau. Les composants qui ont besoin des données peuvent accéder directement au contexte.
3. État global (Global State) : Des bibliothèques de gestion d'état global comme Redux ou MobX peuvent être utilisées pour stocker et accéder aux données partagées sans avoir à les passer en tant que props.

En utilisant ces techniques, vous pouvez éviter le prop drilling et rendre votre code plus lisible, maintenable et réutilisable.

 

