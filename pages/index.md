---
title: Herausforderung
layout: page
---

## Ausgangssituation

In dieser Challenge geht es um ein Vue Pattern, das es ermöglicht, unabhängig von Parent-Child-Beziehungen zwischen Komponenten Events zu versenden und darauf reagieren zu können.

Neben der üblichen Komponente `Challenge.vue` findest Du eine weitere Komponente `Playground.vue`. Diese letzere Komponente wurde bereits vorbereitet und zweifach in der `Challenge.vue` eingebunden.

Die Komponente selbst enthält einen HTML5-Canvas und zeichnet bei Mausklick wahlweise ein Rechteck oder einen Kreise an der angeklickten Stelle.

## Deine Aufgabe

Bearbeite die Datei `components/Challenge.vue` sowie `components/Playground.vue` und implementiere folgende Funktionen:

1. Jeder Playground-Canvas reagiert auf einen Mausklick
2. Je nach Konfiguration des Playground-Komponentenattributes 'position' wird auf dem betreffenden Canvas entweder ein Rechteck oder ein Kreis gezeichnet
3. Erweiter die Funktion, so dass nicht nur der angeklickte Canvas selbst den Klickpunkt zeichnet, sondern auch seine Nachbar-Playground-Komponente quasi synchron.

## Geschätzter Zeitaufwand zur Implementierung

_Ca. 20 Minuten_

**Happy coding 8-)**
