
Une [[struct]] en C est un type de donnée personnalisé qui permet de combiner des données de types différents ensemble. C'est super utile quand tu veux regrouper des données qui sont liées. Par exemple, si tu veux décrire une voiture, tu peux utiliser une struct pour combiner l'année, la marque, la couleur et plein d'autres infos en un seul objet. 

Voici comment tu déclares une struct :

```c
struct s_car
{
	int year;
	char *brand;
	char *color;
};
```

Là, tu viens de créer une struct qui représente une voiture. Chaque voiture a une année (`year`), une marque (`brand`) et une couleur (`color`).

Maintenant, tu peux créer une nouvelle voiture comme ça :

```c
struct s_car myCar = {2018, "Tesla", "Red"};
```

Et voilà! Maintenant, `myCar` est une struct qui contient toutes les infos de ta voiture. 

Si tu veux accéder à une partie spécifique de la struct, tu utilises un `.`. Par exemple, si tu veux savoir l'année de `myCar`, tu fais `myCar.year`.

Si tu as un pointeur vers une struct, tu utilises `->` pour accéder aux éléments. Par exemple, si `p` est un pointeur vers `myCar`, tu fais `p->year` pour obtenir l'année. 


En langage C, une structure (ou struct) est une collection de variables de différents types qui sont regroupées sous un même nom. Les structures sont utilisées pour représenter une entité ayant plusieurs attributs ou propriétés. Elles vous permettent de regrouper des éléments de données apparentés en une seule variable.

Voici comment vous définiriez une structure pour une personne :

```c
struct Personne {
    char nom[50];
    int age;
    double salaire;
};
```

Ici, `struct Personne` est une nouvelle structure de données que vous avez définie. Elle comprend trois membres : `nom` (un tableau de caractères), `age` (un entier) et `salaire` (un nombre à virgule flottante).

Pour déclarer une variable de type `struct Personne`, vous pouvez utiliser la déclaration suivante :

```c
struct Personne personne1;
```

Et vous pouvez accéder aux membres de la structure en utilisant l'opérateur point (`.`) :

```c
strcpy(personne1.nom, "Jean");
personne1.age = 30;
personne1.salaire = 45000.00;
```

Les structures sont souvent utilisées lorsque vous devez regrouper des données apparentées. Par exemple, une base de données d'étudiants pourrait utiliser une structure pour représenter chaque étudiant, avec des membres pour le nom, l'ID de l'étudiant, la majorité, etc.

Les structures peuvent également contenir d'autres structures ou même des pointeurs vers leurs propres types, ce qui les rend très puissantes pour la création de structures de données complexes comme les listes liées et les arbres.

Dans certains cas, vous pouvez également vouloir créer des pointeurs vers des structures. Par exemple :

```c
struct Personne *ptr_personne;
ptr_personne = &personne1;
```

Dans ce cas, vous pouvez accéder aux membres de la structure en utilisant l'opérateur flèche (`->`):

```c
strcpy(ptr_personne->nom, "Jean");
ptr_personne->age = 30;
ptr_personne->salaire = 45000.00;
```

En somme, les structures sont un outil très important pour la création de programmes en langage C, et leur maîtrise est essentielle pour tout programmeur en C.