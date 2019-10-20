+++
title = "Anbindung"
weight = 13
+++

## 4.3 Die Anbindung

DokChess besitzt keine grafische Benutzeroberfläche; die Kommunikation erfolgt stattdessen über die Standardein­- und -­ausgabe.
Als Kommunikationsprotokoll kommt das textbasierte XBoard-­Protokoll zum Einsatz ([→ Entscheidung 9.1 „Wie kommuniziert die Engine mit der Außenwelt?“](/09_entscheidungen/01_anbindung/)).
DokChess lässt sich interaktiv per Kommandozeile bedienen, wenn man die XBoard­-Kommandos kennt und die Engine-Antworten zu deuten weiß ([→ Konzept 8.3 „Benutzungsoberfläche“](/08_konzepte/03_benutzungsoberflaeche/)), siehe folgendes Bild.

![DokChess über die Kommandozeile bedienen](/images/Abb09_07_DokChess_Kommandozeile.png "DokChess über die Kommandozeile bedienen")

Die eigentliche Engine von DokChess wird dabei über einen reaktiven Ansatz („Reactive Extensions“) angebunden ([→ 6. Laufzeitsicht, „Zugermittlung Walkthrough“](/06_laufzeitsicht/01_zugermittlung/)).
DokChess bleibt so auch während der Zugermittlung ansprechbar, ein Benutzer kann zum Beispiel ein sofortiges Ziehen erzwingen.

Die Integration von DokChess in ein UI erfolgt unter Windows über eine Batch­-Datei (_\*.bat_), welche die Java Virtual Machine (JVM) unter Angabe der Klasse mit _main_ Methode startet ([→ 7. Verteilungssicht](/07_verteilungssicht/)).
