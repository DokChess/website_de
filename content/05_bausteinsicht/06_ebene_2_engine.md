+++
title = "Ebene 2: Engine"
pre = "5.6 "
weight = 16
+++

## 5.6 Ebene 2: Engine (Whitebox)

Die Engine zerfällt wie in der folgenden Abbildung dargestellt in Zugsuche und Stellungsbewertung.
Falls vorhanden wird die Ermittlung des Zuges zunächst an die Eröffnungsbibliothek delegiert.
Nur wenn diese keinen Rat weiß, kommt die Zugsuche zum Einsatz.

![Subsystem Engine, Bausteinsicht, Ebene 2](/images/Abb09_13_Subsystem_Engine.png "Subsystem Engine, Bausteinsicht, Ebene 2")
*Bild: Subsystem Engine, Bausteinsicht, Ebene 2*

----

| Modul | Kurzbeschreibung |
|-------|------------------|
| [Zugsuche](/05_bausteinsicht/07_zugsuche/) | Ermittelt zu einer Stellung den unter bestimmten Bedingungen optimalen Zug.|
| [Stellungsbewertung](/05_bausteinsicht/08_stellungsbewertung/) | Bewertet eine Stellung aus Sicht eines Spielers.|
*Tabelle: Module des Subsystems Engine*
