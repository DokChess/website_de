+++
title = "Iteration 1: Durchstich"
weight = 11
+++

### Iterationsziel

Die Engine interagiert mit menschlichem Spieler über ein graphisches Frontend. Es entwickelt sich eine "Partie" über mehrere Züge.

### Zentrale Entscheidungen

* Darstellung der Spielsituation ("Stellung")
* Auswahl eines graphischen Frontends

### Implementierungsaufgaben

* Darstellung des "Brettes", Felder, Züge, etc.
* Anbindung an das graphische Frontend
* Trivialer Zuggenerator

### Inspiration durch DokChess
* Das Domänenmodell von DokChess stellt eine Möglichkeit dar, Spielsituationen in Datenstrukturen zu beschreiben. Hier finden Sie einen Überblick ("8.2 Schach-Domänenmodell").
* Die Entscheidung für XBoard als Kommunikationsprotokoll, um DokChess an grafische Frontends anzubinden, können Sie hier nachlesen ("9.1 Wie kommuniziert die Engine mit der Außenwelt?"). Dort werden auch Alternativen diskutiert.
* Die Art der Kommunikation zwischen DokChess und einem grafischen Frontend ist in einem der Konzepte erläutert: "8.3 Benutzungsoberfläche", Sie finden es hier.
