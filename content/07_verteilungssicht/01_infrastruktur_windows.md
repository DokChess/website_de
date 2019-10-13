+++
title = "Infrastruktur Windows"
weight = 11
+++

## 7.1 Infrastruktur Windows

Das Verteilungsdiagramm im Bild unten zeigt den Einsatz von DokChess unter Windows ohne Eröffnungsbibliothek. Als Frontend wird exemplarisch Arena verwendet ([→ Entscheidung 9.1 „Wie kommuniziert die Engine mit der Außenwelt?“](/09_entscheidungen/01_anbindung/)).

![Deployment von DokChess auf einem Windows-PC](/images/Abb09_17_DeploymentDokChess.png "Deployment von DokChess auf einem Windows-PC")
*Bild:	Deployment von DokChess auf einem Windows-PC*

Software-Voraussetzungen auf dem PC:

* Java Runtime Environment SE 7 (oder höher)
* Die JVM (javaw.exe) muss im Pfad liegen, ansonsten ist dokchess.bat anzupassen
* Arena (siehe http://www.playwitharena.de)

_DokChess.jar_ enthält den kompilierten Java-Quelltext sämtlicher Module und alle nötigen Abhängigkeiten („Über-jar“). Die Script-Datei dokchess.bat startet die Java Virtual Machine mit DokChess.
Beides liegt auf dem Rechner in einem gemeinsamen Verzeichnis, da _dokchess.bat_ die jar-Datei relativ anspricht.

Innerhalb von Arena wird die Skript-Datei im (deutschen) Menü unter "Motoren|Neuen Motor installieren..." bekannt gemacht. Es erscheint eine Dateiauswahl, deren Dateityp sich auf \*.bat-Dateien einschränken lässt. Anschließend ist als Motoren-Typ "Winboard" auszuwählen. Bei anderen Schach-Frontends erfolgt das Bekanntmachen einer Engine ähnlich, vgl. deren Dokumentation.

### Offene Punkte
Einige Frontends unter Windows erlauben lediglich das Einbinden einer \*.exe-Datei als Engine. In diesem Fall müsste DokChess geeignet gewrappt werden.
