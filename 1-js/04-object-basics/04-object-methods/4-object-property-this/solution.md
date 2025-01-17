**Réponse : une erreur.**

Essayez le :
```js run
function makeUser() {
  return {
    name: "John",
    ref: this
  };
};

let user = makeUser();

alert( user.ref.name ); // Erreur: Impossible de lire la propriété 'nom' de undefined
```

C'est parce que les règles qui définissent `this` ne prennent pas en compte la définition d'objet. Seul le moment de l'appel compte.

Ici, la valeur de `this` à l'intérieur de `makeUser()` est `undefined`, car elle est appelée en tant que fonction et non en tant que méthode avec la syntaxe au "point".

La valeur de `this` est un pour toute la fonction, les blocs de code et les littéraux d'objet ne l'affectent pas.

Donc `ref: this` prend actuellement le `this` courant de la fonction.

Voici le cas contraire :

```js run
function makeUser() {
  return {
    name: "John",
*!*
    ref() {
      return this;
    }
*/!*
  };
};

let user = makeUser();

alert( user.ref().name ); // John
```

Maintenant cela fonctionne parce que `user.ref()` est une méthode. Et la valeur de `this` est définie pour l'objet avant le point `.`.

