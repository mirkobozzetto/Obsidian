
## En React, les formulaires permettent de récupérer des données saisies par l'utilisateur et de les envoyer à une API ou de les traiter de manière à effectuer une action.

Pour créer un #formulaire en React, vous pouvez utiliser la balise `<form>`. Vous pouvez alors ajouter des éléments de formulaire tels que des champs de texte, des boutons de soumission, etc. à l'aide de balises HTML standard telles que `<input>`, `<textarea>` et `<button>`.

La propriété `onSubmit` est un gestionnaire d'événements qui se déclenche lorsque le formulaire est soumis (c'est-à-dire lorsque l'utilisateur clique sur le bouton de soumission ou appuie sur la touche Entrée). Vous pouvez utiliser cette propriété pour définir une fonction qui sera exécutée lorsque le formulaire est soumis, ce qui vous permet de traiter les données saisies par l'utilisateur ou de les envoyer à une #API.

`useRef` est une fonction de réaction qui retourne un #objet de référence. Vous pouvez utiliser cet objet de référence pour #stocker une référence à un élément du DOM (c'est-à-dire un élément HTML dans votre page web) ou à une valeur JavaScript. Par exemple, vous pouvez utiliser `useRef` pour créer une référence à un champ de formulaire, comme un champ de texte ou une zone de texte, et utiliser cette référence pour accéder à la valeur de ce champ de formulaire dans votre code.

Voici un exemple de formulaire en React qui utilise `useRef` et `onSubmit` :

```jsx
import { useRef } from 'react';

function MyForm() {
  // Créer une référence au champ de formulaire
  const usernameRef = useRef();

  // Définir une fonction qui sera exécutée lorsque le formulaire est soumis
  const handleSubmit = (event) => {
    event.preventDefault();
    // Accéder à la valeur du champ de formulaire en utilisant la référence
    const username = usernameRef.current.value;
    // Traiter ou envoyer la valeur du champ de formulaire
    // ...
  }

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Nom d'utilisateur :
        <input type="text" ref={usernameRef} />
      </label>
      <button type="submit">Envoyer</button>
    </form>
  );
}

```



Dans cet exemple, nous avons créé une référence à un champ de formulaire en utilisant `useRef` et l'avons affectée à l'élément `input` 