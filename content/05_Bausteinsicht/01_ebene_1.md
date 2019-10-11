+++
title = "Ebene 1"
weight = 11
+++

## 5.1	Ebene 1

DokChess zerfällt wie in Bild unten dargestellt in vier Subsysteme. Die gestrichelten Pfeile stellen fachliche Abhängigkeiten der Subsysteme untereinander dar ("x -> y" für "x ist abhängig von y"). Die Kästchen auf der Membran des Systems sind Interaktionspunkte mit Außenstehenden (→ <a href="/03_kontextabgrenzung/02_technischer_kontext/">Kontextabgrenzung 3.2</a>).

![DokChess, Bausteinsicht, Ebene 1](/images/Abb09_08_Bausteinsicht_Ebene1.png "DokChess, Bausteinsicht, Ebene 1")
*Bild: DokChess, Bausteinsicht, Ebene 1*


*Tabelle: Überblick über Subsysteme von DokChess*

| Subsystem | Kurzbeschreibung |
|-----------|------------------|
| XBoard-Protokoll | Realisiert die Kommunikation mit einem Client mit Hilfe des XBoard-Protokolls. |
| Spielregeln | Beinhaltet die Schachregeln und kann z.B. zu einer Stellung alle gültigen Züge ermitteln. |
| Engine | Beinhaltet die Ermittlung eines nächsten Zuges ausgehend von einer Spielsituation. |
| Eröffnung | Stellt Züge aus der Eröffnungsliteratur zu einer Spielsituation bereit.|
