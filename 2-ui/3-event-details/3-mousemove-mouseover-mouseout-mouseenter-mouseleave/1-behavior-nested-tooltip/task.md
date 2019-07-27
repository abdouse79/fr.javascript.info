importance: 5

---

# Comportement amélioré d'une info-bulle 

Ecrivez un code en JavaScript montrant une info-bulle sur un élément  avec l'attribut `data-tooltip`.

C'est comme la tache <info:task/behavior-tooltip>, mais ici les éléments annotes peuvent être  imbriques. L'info-bulle la plus imbriquée est montrée.

Par example:

```html
<div data-tooltip="Here – is the house interior" id="house">
  <div data-tooltip="Here – is the roof" id="roof"></div>
  ...
  <a href="https://en.wikipedia.org/wiki/The_Three_Little_Pigs" data-tooltip="Read on…">Survolez moi</a>
</div>
```

Le résultat dans l'iframe:

[iframe src="solution" height=300 border=1]

P.S. Astuce: une seule info-bulle peut être montrée à la fois.
