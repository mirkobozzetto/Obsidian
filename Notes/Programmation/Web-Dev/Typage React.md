en #tsx on définit les #types dans des #objet  par exemple on pourrait créer un type UserProps et lui donner les propriétés name: string et phone?: number

```tsx
type UserProps = { name: string; phone?: number; };

const UserComponent = (props: UserProps) => { // ... };
```

il y a aussi ce qu'on appelles les types #union 

```tsx
type AvatarVariant = 'primary' | 'secondary';
````
 si j'ai des erreurs de typage lors d'un #event je peux utiliser cette convention de nommage  à la fin de mon object de type
 
 & ComponentPropsWithoutRef<"div"> par exemple comme ceci
 
 ```tsx
 type AvatarProps = {

username: string;

avatarUrl: string;

className?: string;

} & ComponentPropsWithoutRef<"div">
```

