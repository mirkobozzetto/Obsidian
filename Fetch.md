#fetch  #projets #React  #API 

# Fetch et timeout

## répupération de données sur une api 

### Une boucle qui parcours les éléménets tu tables va afficher des cards 

Tout d'abord je vais choisir une api comme twitter, ou même une api bidopnne de citations

je vais aller récupérer un élément aléatoire sur une list pour l'afficher et réaliser son rendu avec une petite animation de sorte à afficher le suivant après un delai de 3/4 secondes.

La card s'affichera et au bout de 3 secondes elle sera mise à jour etc

J'utiliserain #useState   dans ma fonction qui #fetch pour récupérer la citation par exemple, 
et je peux éventuellement mettre en place un système de gestion d'erreurs avec try catch..

Pour ce qui est du delai à attendre pour passer à la card suivante j'utiliserai 
le #Hook #useEffect  que j'appellerai en #fonction_anonyme `() => {`
en y appellant la fonction précédente un peux comme ceci par exemple 

```jsx
useEffect(() => {
fetchCitation(); 
const intervalId = setInterval(fetchCitation, 4000); 

return () => clearInterval(intervalId);
}, []);
```


