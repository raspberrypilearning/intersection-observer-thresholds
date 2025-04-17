De Intersection Observator wordt gebruikt om te detecteren wanneer een element (bijv. `<img>`, `<p>` of `<div>`) de browserviewport van de gebruiker binnenkomt of verlaat.

Je kunt ook opties toevoegen aan de observer, zoals het instellen van een drempel.

Drempelwaarden variëren van `0` tot `1`

`1` betekent dat elke afzonderlijke pixel van het element in de viewport moet staan om de callback te kunnen uitvoeren.

`0` is de standaardwaarde en betekent dat slechts één pixel er in hoeft te staan om de callback te laten werken.

Hier is een voorbeeld van het gebruik van de optie `threshold` (drempel) in een intersection observer in het project [Geanimeerd verhaal](https://projects.raspberrypi.org/nl-NL/projects/animated-story) (onderdeel van het pad [Meer Web](https://projects.raspberrypi.org/nl-NL/raspberrypi/more-web)).

De optie `threshold: 1` in dit voorbeeld betekent de callback alleen wordt uitgevoerd wanneer de hele afbeelding van de slak in de viewport staat.

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
