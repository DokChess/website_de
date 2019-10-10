+++
title = "Wohin noch?"
weight = 14
+++

Ausgehend vom Ergebnis der dritten Iteration gibt es viele Möglichkeiten, Ihre Engine zu verbessern. Die Optionen fallen grob in zwei Gruppen: Die Erhöhung der Suchtiefe für die Zugauswahl und das Hinzufügen von Wissen. Ich liste im Folgenden die wichtigsten Optionen auf.

### Erhöhen der Suchtiefe

* Effizientere Datenstrukturen
* Bessere Suchalgorithmen (Alpha-Beta-Suche ist in DokChess bereits enthalten)
* Caching (Zuggenerator, Teilbäume, Transpositionen)
* Nebenläufigkeit (Ausnutzen des Denkens des Gegners, Parallelisierung der Zugermittlung)

### Hinzufügen von Wissen

* Eröffnungen (DokChess nutzt dies bereits, siehe Bausteinsicht)
* Endspiele
* Strategische Themen (Entwicklung, Zentrumsbeherrschung, ...). können teilweise über bessere Stellungsbewertung erreicht werden
