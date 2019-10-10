+++
title = "Die Anbindung"
weight = 13
+++

DokChess besitzt keine grafische Benutzeroberfläche; die Kommunikation erfolgt stattdessen über die Standardein­- und -­ausgabe. Als Kommunikationsprotokoll kommt das textbasierte XBoard-­Protokoll zum Einsatz (→ Entscheidung 9.1 „Wie kommuniziert die Engine mit der Außenwelt?“). DokChess lässt sich interaktiv per Kommandozeile bedienen, wenn man die XBoard­-Kommandos kennt und die Engine-Antworten zu deuten weiß (→ Konzept 8.3 „Benutzungsoberfläche“), siehe folgendes Bild.

![DokChess über die Kommandozeile bedienen](/images/Abb09_07_DokChess_Kommandozeile.png "DokChess über die Kommandozeile bedienen")

Die eigentliche Engine von DokChess wird dabei über einen reaktiven Ansatz („Reactive Extensions“) angebunden (→ 6. Laufzeitsicht, „Zugermittlung Walkthrough“). DokChess bleibt so auch während der Zugermittlung ansprechbar, ein Benutzer kann zum Beispiel ein sofortiges Ziehen erzwingen. Die Integration von DokChess in ein UI erfolgt unter Windows über eine Batch­-Datei (\*.bat), welche die Java Virtual Machine (JVM) unter Angabe der Klasse mit main­-Methode startet (→ 7. Verteilungssicht).
