L'algorithme est simple: 
1. Attachez les gestionnaires des évènements `onmouseover/out` sur les éléments. Vous pouvez aussi utiliser `onmouseenter/leave` ici, mais ils sont moins universels, ils ne vont pas fonctionner ici si nous introduisons la délégation.
2. Lorsque le curseur de la souris entre en contact avec l'élément, commence à mesurer la vitesse avec l'évènement `mousemove`.
3. Si la vitesse est lente, alors exécute `over`.
4. Plus tard si nous sommes hors de l’élément, et `over` a été exécuté, lance `out`.

La question est: "Comment mesurer la vitesse?"

La première idée serait: d'exécuter notre fonction chaque `100ms` et de mesurer la distance entre les cordonnées précédentes et celles nouvelles. Si elle est petite, alors la vitesse est petite.

Malheureusement, il n'y a aucun moyen d'obtenir "les coordonnées en temps réelle de la souris" en JavaScript. Il n'existe pas de  fonction comme `getCurrentMouseCoordinates()`.

La seule manière d'obtenir les coordonnées est d'écouter les évènements de la souris  tel que `mousemove`.

Alors nous pouvons mettre un gestionnaire d'évènement  `mousemove`  pour contrôler les coordonnées et nous souvenir d'elles. Ensuite nous pouvons les comparer une fois chaque `100ms`.

P.S. Notez bien: la solution teste l'usage de `dispatchEvent` pour voir si l'info-bulle fonctionne correctement.
