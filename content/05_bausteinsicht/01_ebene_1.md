+++
title = "Ebene 1"
weight = 11
+++

## 5.1	Ebene 1

DokChess zerfällt wie in Bild unten dargestellt in vier Subsysteme. Die gestrichelten Pfeile stellen fachliche Abhängigkeiten der Subsysteme untereinander dar ("x -> y" für "x ist abhängig von y"). Die Kästchen auf der Membran des Systems sind Interaktionspunkte mit Außenstehenden
([→ 3. Kontextabgrenzung](/03_kontextabgrenzung/02_technischer_kontext/)).

![DokChess, Bausteinsicht, Ebene 1](/images/Abb09_08_Bausteinsicht_Ebene1.png "DokChess, Bausteinsicht, Ebene 1")
*Bild: DokChess, Bausteinsicht, Ebene 1*


*Tabelle: Überblick über Subsysteme von DokChess*

| Subsystem | Kurzbeschreibung |
|-----------|------------------|
| [XBoard-Protokoll](/05_bausteinsicht/02_xboard-protokoll/) | Realisiert die Kommunikation mit einem Client mit Hilfe des XBoard-Protokolls. |
| [Spielregeln](/05_bausteinsicht/03_spielregeln/) | Beinhaltet die Schachregeln und kann z.B. zu einer Stellung alle gültigen Züge ermitteln. |
| [Engine](/05_bausteinsicht/04_engine/) | Beinhaltet die Ermittlung eines nächsten Zuges ausgehend von einer Spielsituation. |
| [Eröffnung](/05_bausteinsicht/05_eroeffnung/) | Stellt Züge aus der Eröffnungsliteratur zu einer Spielsituation bereit.|
