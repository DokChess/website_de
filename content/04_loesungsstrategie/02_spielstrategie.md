+++
title = "Spielstrategie"
weight = 12
+++

## 4.2 Spielstrategie

Für die Integration von Eröffnungsbibliotheken wurde das Dateiformat „Polyglot Opening Book“ implementiert ([→ Bausteinsicht 5.5 “Eröffnung“](/05_bausteinsicht/05_eroeffnung/)), DokChess antwortet dadurch zu Beginn mit „Buchwissen“.

Für die Spielstrategie im weiteren Partieverlauf ist ein klassischer [Minimax­-Algorithmus](https://de.wikipedia.org/wiki/Minimax-Algorithmus) mit fester Suchtiefe im Spielbaum verantwortlich.
Dessen Basis-Implementierung ist nicht nebenläufig, die Bewertung einer Stellung an einem Terminalknoten im Spielbaum basiert ausschließlich auf dem Material ([→ Bausteinsicht Ebene 2, 5.6 “Engine“](/05_bausteinsicht/06_ebene_2_engine/)). Diese einfachen Implementierungen erfüllen unter den gegebenen Randbedingungen bereits die Qualitätsszenarien.

Eine [Alpha­-Beta­-Suche](https://de.wikipedia.org/wiki/Alpha-Beta-Suche) illustriert den einfachen Austausch von Algorithmen. Spielstärke und/oder Effizienz verbessern sich durch die bei gleicher Rechenzeit tiefere Suche im Baum erheblich. Die unveränderlichen Datenstrukturen in DokChess erleichtern auch das Implementieren nebenläufiger Algorithmen; ein paralleler Minimax ist ebenfalls als Beispiel enthalten.
