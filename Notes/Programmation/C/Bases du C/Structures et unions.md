Bien sûr, les structures (`struct`) et les unions (`union`) sont des types de données définis par l'utilisateur en C. Ils permettent de regrouper des variables de différents types.

**1. Structures (`struct`) :**

Une structure est une collection de variables de différents types. Par exemple, vous pouvez créer une structure `Personne` pour représenter une personne :

```c
struct Personne {
    char nom[50];
    int age;
    float taille;
};
```

Vous pouvez alors créer une variable de type `Personne` et accéder à ses membres avec l'opérateur `.` :

```c
struct Personne john;
strcpy(john.nom, "John Doe");
john.age = 30;
john.taille = 1.75;

printf("Nom: %s, Age: %d, Taille: %.2f", john.nom, john.age, john.taille);
```

Les structures sont utilisées quand vous voulez regrouper des données qui sont naturellement liées, comme les différentes caractéristiques d'une personne.

**2. Unions (`union`) :**

Une union est similaire à une structure, mais elle peut stocker une seule valeur à la fois. C'est-à-dire qu'une union a la taille du plus grand de ses membres et qu'un seul de ses membres peut contenir une valeur à un moment donné.

```c
union Valeur {
    int i;
    float f;
    char str[20];
};
```

Vous pouvez alors créer une variable de type `Valeur` et y stocker différentes sortes de valeurs :

```c
union Valeur v;

v.i = 10;
printf("v.i : %d\n", v.i);

v.f = 220.5;
printf("v.f : %.2f\n", v.f);

strcpy(v.str, "C Programming");
printf("v.str : %s\n", v.str);
```

Cependant, puisque l'union peut stocker une seule valeur à la fois, seule la valeur `"C Programming"` est conservée à la fin.

Les unions sont moins utilisées que les structures, mais elles peuvent être utiles dans certains cas, par exemple quand vous voulez économiser de la mémoire en stockant différentes sortes de données dans le même espace mémoire.

Enfin, il convient de mentionner que C vous permet de créer des pointeurs vers des structures et des unions, ce qui est souvent utilisé pour créer des structures de données plus complexes comme des listes, des arbres et des graphes.