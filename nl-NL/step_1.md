The intersection observer is used to detect when an element (e.g. `<img>`, `<p>`, or `<div>`) enters or leaves the user's browser viewport.

Je kunt ook opties toevoegen aan de observer, zoals het instellen van een drempel.

Threshold values range from `0` to `1`.

`1` betekent dat elke afzonderlijke pixel van het element in de viewport moet staan om de callback te kunnen uitvoeren.

`0` is de standaardwaarde en betekent dat slechts één pixel er in hoeft te staan om de callback te laten werken.

Here is an example of how the `threshold` option is used in an intersection observer in the [Animated story](https://projects.raspberrypi.org/en/projects/animated-story) project (part of the [More web](https://projects.raspberrypi.org/en/raspberrypi/more-web) path).

De optie `threshold: 1` in dit voorbeeld betekent de callback alleen wordt uitgevoerd wanneer de hele afbeelding van de slak in de viewport staat.

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
