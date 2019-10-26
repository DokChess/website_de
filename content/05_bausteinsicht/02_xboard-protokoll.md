+++
title = "XBoard-Protokoll"
weight = 12
+++

## 5.2 XBoard-Protokoll (Blackbox)

### Zweck/Verantwortlichkeit

Dieses Subsystem realisiert die Kommunikation mit einem Client (z.B. einer grafischen Oberfläche) mit Hilfe des textbasierten XBoard-Protokolls ([→ Entscheidung 9.1](/09_entscheidungen/01_anbindung/)).
Das Subsystem liest Befehle über die Standardeingabe ein, prüft sie gegen die Spielregeln und setzt sie für die Engine um.
Antworten der Engine (insbesondere ihre Züge) werden vom Subsystem als Ereignisse entgegengenommen, gemäß Protokoll formatiert und über die Standardausgabe zurückgesendet.
Das Subsystem treibt somit das ganze Spielgeschehen. Es enthält auch die main-Methode.

### Schnittstellen

Das Subsystem stellt seine Funktionalität über die Java-Klassen _de.dokchess.xboard.XBoard_ und _de.dokchess.xboard.Main_ bereit:

![Klassen XBoard und Main](/images/Abb09_09_Schnittstellen_Xboard.png "Klassen XBoard und Main")
*Bild: Klassen XBoard und Main*

----

| Methode | Kurzbeschreibung |
|---------|------------------|
| setEingabe | Setzt die Protokoll-Eingabe per Dependency Injection ([→ Konzept 8.1](/08_konzepte/01_abhaengigkeiten/)). Typischerweise ist das die Standardeingabe (stdin), automatische Tests z.B. verwenden eine andere Quelle. |
| setAusgabe | Setzt die Protokoll-Ausgabe. Typischerweise ist das die Standardausgabe (stdout), automatische Tests verwenden eine andere Senke.
| setSpielregeln | Setzt eine Implementierung der Spielregeln, [→ 5.3 Spielregeln (Blackbox)](/05_bausteinsicht/03_spielregeln/)
| setEngine | Setzt eine Implementierung der Engine, [→ 5.4 Engine (Blackbox)](/05_bausteinsicht/04_engine/) |
| spielen | Startet die eigentliche Kommunikation (Eingabe/Verarbeitung/Ausgabe) in einer Endlosschleife, bis zum Beenden-Kommando.|
*Tabelle: Methoden der Klasse XBoard*


### Ablageort / Datei
Die Implementierung liegt unterhalb der Pakete   
_de.dokchess.xboard..._


### Offene Punkte
Die Implementierung des Protokolls ist unvollständig.
Sie reicht aber für die an DokChess gestellten Anforderungen aus.
Insbesondere werden folgende Features nicht unterstützt:

* Zeitkontrolle
* Permanent Brain (Denken, auch während der andere denkt)
* Remis-Angebote und Aufgabe des Gegners
* Schach-Varianten (alternative Regeln, z.B. Schach960)
