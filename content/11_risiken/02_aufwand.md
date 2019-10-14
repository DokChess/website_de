+++
title = "Aufwand"
weight = 2
+++

## 11.2 Risiko: Aufwand der Implementierung
Es liegt keinerlei Erfahrung mit der Schachprogrammierung vor. Gleichzeitig wirken die Spielregeln, die komplett realisiert werden sollen (vgl. Aufgabenstellung), umfangreich und kompliziert. Die Figurenarten ziehen unterschiedlich, hinzu kommen Spezialregeln wie Patt und Umwandlung. Bei Rochade und en passant ist die Partiehistorie, und nicht nur die aktuelle Situation auf dem Brett relevant.
Die Programmierung der Algorithmen ist ebenfalls nicht-trivial.
Für die Anbindung von Eröffnungsbibliotheken und Endspieldatenbanken ist eine umfangreiche Recherche erforderlich.
Die Implementierung von DokChess verläuft nebenher in der Freizeit. Es ist unklar, ob die Zeit reicht, um innerhalb des Zeitplans ([→ Randbedingungen 2.2](/02_randbedingungen/02_organisatorisch/)) vorzeigbare Ergebnisse zu präsentieren.

### Eventualfallplanung
Falls zu den Vorträgen in März und Mai 2011 keine lauffähige Fassung vorliegt, könnte eine Live-Demonstration entfallen. Der kostenlose Abendvortrag bei oose im März könnte sogar komplett abgesagt werden (Schaden: Image-Verlust).

### Risikominderung
Der Aufwand wird dadurch reduziert, dass folgende Spielregeln zunächst nicht implementiert werden:

- 50-Züge-Regel
- Stellungswiederholung

Das Fehlen hat geringe Konsequenzen bezüglich der Spielstärke, und keine bezüglich der Korrektheit des Spiels der Engine.
Die Anbindung von Eröffnungsbibliotheken und Endspieldatenbanken wird niedrig priorisiert und hinten angestellt.
