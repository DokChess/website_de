+++
title = "Spielstärke"
menuTitle = "11.3 Spielstärke"
weight = 3
+++

## 11.3 Risiko: Erreichen der Spielstärke
Die Qualitätsziele fordern sowohl eine akzeptable Spielstärke wie auch eine einfache, leicht zugängliche Lösung.
Zudem gibt es Anforderungen bezüglich Effizienz.
Es ist unsicher, ob die anvisierte Java-Lösung mit objektorientiertem Domänenmodell und einfacher Zugauswahl diese konkurrierenden Ziele erreichen kann.

Das Risiko manifestiert sich durch zu schlechte Spielstärke, zu lange Wartezeiten oder beides.
Insbesondere bei Live-Vorführungen in Vorträgen wäre das unschön, da die Lösung dann von den Zuhörern gar nicht als solche wahrgenommen wird (sondern als Spielerei).

Unklar ist, ab wann eine Spielstärke als unangemessen schwach angesehen wird.

### Eventualfallplanung
In Vorträgen könnte auf Teile der Live-Demonstration verzichtet werden.
Ggf. werden im Vorfeld gespielte Partien gezeigt.

### Risikominderung
Mit Hilfe geeigneter Szenarien werden die Qualitätsziele konkretisiert.
Im Anschluss entwickeln wir mit Hilfe von Schachliteratur (konkret Schachaufgaben) Testfälle (Unit-Tests), die präzisieren, welche Spielstärke erwartet werden kann.
So kann zumindest früh ermittelt werden, wo die Engine steht.
