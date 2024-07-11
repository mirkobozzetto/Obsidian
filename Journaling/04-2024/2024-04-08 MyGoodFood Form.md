Tag:  #daily #mygoodfood #formulaires #openai #react-hook-form #zod

Je vais devoir créer un formulaire qui génèrera une string.
je vais utiliser le retour de cette string comme requête à openai pour générer mon formulaire.

Pour cela je vais me servir de React Hook Form et sécuriser le typage avec Zod.

Je dois tester tout ça et récupérer les données dans la db Postgres afin de pouvoir permettre à l'utilisateur de consulter ses données à tout moment dans son espace membre,

Il pourrait bien sûr modifier ses données à tout moment  afin de générer la liste de courses diféremment en fonction de ses besoins

Une autre idée serait de garder en cache les préférences afin d'en informer openai lors de la requête dans le but de ne pas avoir de listes de courses trop redondantes si l'utilisateur décide d'avoir des des variétés de choses plus intéressantes pour lui.

on pourrait afficher au moment de faire la requête de courses ce qui a été mis lors de la fois précédente afin de permettre de changer ses préférences à tout moment 

Et à cet effet on pourrait générer un messages proches de box de formulaire de manière animée afin d'attirer l'attention sur le possibles changements
