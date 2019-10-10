+++
title = "Spielstrategie"
weight = 12
+++

Für die Integration von Eröffnungsbibliotheken wurde das Dateiformat „Polyglot Opening Book“ implementiert (→ Bausteinsicht 5.5 “Eröffnung“), DokChess antwortet dadurch zu Beginn mit „Buchwissen“.
Für die Spielstrategie im weiteren Partieverlauf ist ein klassischer Minimax­-Algorithmus mit fester Suchtiefe im Spielbaum verantwortlich. Dessen Basis-Implementierung ist nicht nebenläufig, die Bewertung einer Stellung an einem Terminalknoten im Spielbaum basiert ausschließlich auf dem Material (→ Bausteinsicht Ebene 2, 9.5.6 “Engine“). Diese einfachen Implementierungen erfüllen unter den gegebenen Randbedingungen bereits die Qualitätsszenarien.
Eine Alpha­Beta­-Suche illustriert den einfachen Austausch von Algorithmen. Spielstärke und/oder Effizienz verbessern sich durch die bei gleicher Rechenzeit tiefere Suche im Baum erheblich. Die unveränderlichen Datenstrukturen in DokChess erleichtern auch das Implementieren nebenläufiger Algorithmen; ein paralleler Minimax ist ebenfalls als Beispiel enthalten.
