+++
title = "Ebene 2: Engine"
weight = 16
+++

## 5.6 Ebene 2: Engine (Whitebox)

Die Engine zerfällt wie in der folgenden Abbildung dargestellt in Zugsuche und Stellungsbewertung. Falls vorhanden wird die Ermittlung des Zuges zunächst an die Eröffnungsbibliothek delegiert. Nur wenn diese keinen Rat weiß, kommt die Zugsuche zum Einsatz.

![Subsystem Engine, Bausteinsicht, Ebene 2](/images/Abb09_13_Subsystem_Engine.png "Subsystem Engine, Bausteinsicht, Ebene 2")

*Bild: Subsystem Engine, Bausteinsicht, Ebene 2*

*Tabelle: Module des Subsystems Engine*

| Modul | Kurzbeschreibung |
|-------|------------------|
| Zugsuche | Ermittelt zu einer Stellung den unter bestimmten Bedingungen optimalen Zug.|
| Stellungsbewertung | Bewertet eine Stellung aus Sicht eines Spielers.|
