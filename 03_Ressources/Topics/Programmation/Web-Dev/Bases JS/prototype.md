
Les propriétés `prototype` sont utilisées dans JavaScript pour ajouter des méthodes et des propriétés à des objets. Chaque fonction en JavaScript possède une propriété `prototype` par défaut, qui est un objet vide. Vous pouvez étendre ce prototype en y ajoutant des méthodes et des propriétés, et ces méthodes et propriétés seront ensuite disponibles pour tous les objets créés à partir de cette fonction en utilisant le mot-clé [[new]].

Voici comment utiliser les propriétés `prototype` en JavaScript :

1. Ajout de méthodes au prototype :

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.sayHello = function() {
  console.log("Bonjour, je m'appelle " + this.name);
};

var person1 = new Person("Alice");
person1.sayHello(); // Affiche "Bonjour, je m'appelle Alice"

var person2 = new Person("Bob");
person2.sayHello(); // Affiche "Bonjour, je m'appelle Bob"
```

Dans cet exemple, la méthode `sayHello` est ajoutée au prototype de la fonction `Person`. Lorsque de nouveaux objets sont créés avec `new Person()`, ils héritent de cette méthode depuis le prototype.

2. Ajout de propriétés au prototype :

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.age = 25;

var person1 = new Person("Alice");
console.log(person1.age); // Affiche 25

var person2 = new Person("Bob");
console.log(person2.age); // Affiche 25

person1.age = 30;
console.log(person1.age); // Affiche 30 (la propriété est masquée par la valeur définie sur l'objet)
console.log(person2.age); // Affiche 25 (la valeur d'origine sur le prototype est préservée)
```

Dans cet exemple, la propriété `age` est ajoutée au prototype de la fonction `Person`. Tous les objets créés à partir de `Person` auront cette propriété par défaut. Cependant, la valeur de la propriété peut être modifiée spécifiquement sur chaque objet sans affecter la valeur d'origine sur le prototype.

L'utilisation de `prototype` permet de partager efficacement des méthodes et des propriétés entre plusieurs objets créés à partir de la même fonction, ce qui peut économiser de la mémoire et améliorer les performances de l'application. C'est également la base de l'héritage des objets en JavaScript.