+++
title = "Einstieg"
weight = 10
+++

Die folgende Tabelle stellt die Qualitätsziele von DokChess (siehe Abschnitt 1.2) passenden Architekturansätzen gegenüber, und erleichtert so einen Einstieg in die Lösung.

| Qualitätsziel | Dem zuträgliche Ansätze in der Architektur |
|---------------|--------------------------------------------|
Zugängliches Beispiel (Analysierbarkeit) | <ul><li>Architekturüberblick gegliedert nach arc42<li>Explizites, objektorientiertes Domänenmodell<li>Modul-, Klassen- und Methodennamen in Deutsch, um englische Schachbegriffe zu vermeiden<li>Ausführliche Dokumentation der öffentlichen Schnittstellen in javadoc</ul> |
| Einladende Experimentierplattform (Änderbarkeit)|<ul><li>verbreitete Programmiersprache Java, →(a)<li>Schnittstellen für Kernabstraktionen (z.B. Stellungsbewertung, Spielregeln)<li>Unveränderliche Objekte (Stellung, Zug, ...) erleichtern Implementierung vieler Algorithmen<li>„Zusammenstecken“ der Bestandteile mit Dependency Injection führt zu Austauschbarkeit, →(b)<li>Hohe Testabdeckung als Sicherheitsnetz</ul>|
|Bestehende Frontends nutzen (Interoperabilität)|<ul><li>Verwendung des verbreiteten Kommunikationsprotokolls xboard, →\(c\), <li>Einsatz des portablen Java, →(a)</ul>|
|Attraktive Spielstärke (Attraktivität)|<ul><li>Integration von Eröffnungsbibliotheken →(d)<li>Implementierung des Minimax-Algorithmus und einer geeigneter Stellungsbewertung, →(e)<li>Integrationstests mit Schachaufgaben für taktische Motive und Mattsituationen</ul>|
| Schnelles Antworten auf Züge (Effizienz) |<ul><li>Reactive Extensions für nebenläufige Berechnung mit neu gefundenen besseren Zügen als Events →(f)<li>Optimierung des Minimax durch Alpha-Beta-Suche, →(e)<li>Effiziente Implementierung des Domänenmodells<li>Integrationstests mit Zeitvorgaben</ul>|

Kleine Buchstaben in Klammern →(x) verorten einzelne Ansätze aus der Tabelle im folgenden schematischen Bild. Der restliche Abschnitt 4 führt in wesentliche Architekturaspekte ein und verweist auf weitere Informationen.

![Informelles Überblicksbild für DokChess](/images/Abb09_06_Ueberblick.png "Informelles Überblicksbild für DokChess")
*Bild: Informelles Überblicksbild für DokChess*
