L'Intersection Observer est utilisé pour détecter quand un élément (par exemple `<img>`, `<p>` ou `<div>`) entre ou quitte la fenêtre d'affichage du navigateur de l'utilisateur.

Tu peux également ajouter des options à l'observateur, comme la définition d'un threshold (seuil).

Les valeurs de seuil varient de `0` à `1`

`1` signifie que chaque pixel de l'élément doit être dans la fenêtre d'affichage pour que le rappel s'exécute.

`0` est la valeur par défaut et signifie qu'un seul pixel doit se croiser pour que le rappel s'exécute.

Voici un exemple d'utilisation de l'option `threshold` dans un Intersection Observer dans le projet [Histoire animée](https://projects.raspberrypi.org/fr-FR/projects/animated-story) (faisant partie du parcours [Plus de web](https://projects.raspberrypi.org/fr-FR/raspberrypi/more-web)).

L'option `threshold: 1` dans cet exemple signifie que le rappel se déclenche uniquement lorsque toute l'image de l'escargot est dans la fenêtre d'affichage.

--- code ---
---
language: js
filename: 
line_numbers: true
line_number_start: 1
line_highlights: 6
---

const snailObserver = new IntersectionObserver((entries) => {
  if (entries[0].isIntersecting) {
    entries[0].target.classList.add("startCrawl");
  }
},
{ threshold: 1 }
);
snailObserver.observe(document.querySelector("#snail"));

--- /code ---
