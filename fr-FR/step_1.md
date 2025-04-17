The intersection observer is used to detect when an element (e.g. `<img>`, `<p>`, or `<div>`) enters or leaves the user's browser viewport.

Tu peux également ajouter des options à l'observateur, comme la définition d'un threshold (seuil).

Threshold values range from `0` to `1`.

`1` signifie que chaque pixel de l'élément doit être dans la fenêtre d'affichage pour que le rappel s'exécute.

`0` est la valeur par défaut et signifie qu'un seul pixel doit se croiser pour que le rappel s'exécute.

Here is an example of how the `threshold` option is used in an intersection observer in the [Animated story](https://projects.raspberrypi.org/en/projects/animated-story) project (part of the [More web](https://projects.raspberrypi.org/en/raspberrypi/more-web) path).

L'option `threshold: 1` dans cet exemple signifie que le rappel se déclenche uniquement lorsque toute l'image de l'escargot est dans la fenêtre d'affichage.

## --- code ---

language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights: 6
-------------------------------------------------------

const snailObserver = new IntersectionObserver((entries) => {
if (entries[0].isIntersecting) {
entries[0].target.classList.add("startCrawl");
}
},
{ threshold: 1 }
);
snailObserver.observe(document.querySelector("#snail"));

\--- /code ---
