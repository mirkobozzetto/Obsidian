Tag:  #daily #React #props


Un petit rappel ici sur l'utilité et la réutilisabilité des compoosants en React:

Lors de la création de composants tels que des cartes par exemples on pensera à mettre danse les props du composant toutes les informations qui seront sujettes à changer d'un composant à l'autre qu'on aura besoin de dupliquer

```jsx
const Card = ({ image, title, description }) => {
	return (
		<img
		src={image} //
		// ...etc
/>
	)
//ensuite on peu appeler la Card comme ceci grace au porps qu'on remplit
<Card
image="src/img.jpg"
```

