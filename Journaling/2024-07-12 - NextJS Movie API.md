#react #nextjs #api

**[omdb_nextmoovie](https://github.com/mirkobozzetto/omdb_nextmoovie)**


#QueryProvider  s’occupe de récupérer les données pour toi. Tu l’utilises pour éviter de réécrire les mêmes demandes de données partout dans ton application.

C’est comme avoir un assistant qui va chercher ce dont tu as besoin pour que tu n’aies pas à le faire à chaque fois.

#useDebounce est un hook personnalisé qui aide à réduire le nombre de requêtes ou d'actions effectuées en réponse à des événements rapides et répétés. Cela est particulièrement utile pour les entrées de recherche où les utilisateurs peuvent taper rapidement.

#Zustand est comme une boîte où tu ranges et organises facilement toutes les infos de ton application.Tu t’en sers pour conserver et gérer l’état des films dans ton application : les données des films, si des films sont en train de charger, les éventuelles erreurs, et les actions comme la recherche de films. Cela centralise tout ce dont tu as besoin en un seul endroit, facilitant l’accès et la gestion.

#Zod dans ton contexte sert de “garde-frontière” pour tes données.
Il vérifie que chaque donnée reçue ou utilisée dans ton application correspond exactement à ce que tu attends. Si les données ne sont pas correctes, Zod les bloque avant qu’elles ne causent des problèmes dans ton application. Cela te permet de gérer les données de manière sûre et prévisible, évitant les erreurs et les bugs liés à des données inattendues ou mal formées.
C’est comme avoir un contrôle de sécurité qui s’assure que tout est en ordre avant de laisser passer les informations.

Le #hook #useEffect dans React te permet d’effectuer des effets secondaires dans les composants fonctionnels. C’est un peu comme dire à React :
“Après avoir affiché le composant, et à chaque fois que certaines données changent, fais quelque chose en plus.”

Tu utilises #QueryClient pour gérer les données de ton application de manière efficace. #useState crée et garde ce QueryClient.
Ensuite, tu places ce client dans #QueryClientProvider pour que tous les composants enfants puissent facilement accéder aux données et les gérer sans complication.
Cela rend ton app plus rapide et réactive.
