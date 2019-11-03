+++
title = "Domänenmodell"
menuTitle = "8.2 Domänenmodell"
weight = 2
+++

## 8.2 Schach-Domänenmodell

> "Das Schachspiel wird zwischen zwei Gegnern gespielt, die abwechselnd ihre Figuren auf einem quadratischen Spielbrett, Schachbrett genannt, ziehen."
>
> (Zitat aus den FIDE-Regeln)

Die verschiedenen Systemteile tauschen schachspezifische Daten aus.
Hierzu zählen vor allem die Situation auf dem Brett (Stellung), sowie gegnerische und eigene Züge.
Als Aufruf- und Rückgabeparameter werden in allen Modulen dieselben Klassen verwendet.

An dieser Stelle finden Sie einen groben Überblick über diese Datenstrukturen und deren Abhängigkeiten untereinander.
Details sind in der Quelltextdokumentation (javadoc) enthalten.
Die Klassen und Aufzählungstypen (enums) befinden sich im Paket _de.dokchess.allgemein_.

Eine Schachfigur ist gekennzeichnet durch Farbe (schwarz oder weiß) und Art (König, Dame, ...).
Im Domänenmodell von DokChess weiß eine Figur nicht, wo sie steht.
Die Klasse ist unveränderlich (immutable) wie alle anderen im Domänenmodell auch.

![Eine Figur hat eine Farbe und eine Art](/images/Abb09_18_Figur.png "Eine Figur hat eine Farbe \(z.B. weiß\) und eine Art \(z.B. Bauer\)")

*Bild: Eine Figur hat eine Farbe (z.B. weiß) und eine Art (z.B. Bauer)*

Das Schachbrett besteht aus 8 x 8 Feldern die in 8 Reihen (1-8) und 8 Linien (a-h) angeordnet sind. Die Klasse _Feld_ beschreibt ein ebensolches. Da ein Feld maximal von einer Figur besetzt sein kann, reicht für die Angabe eines Zuges, von wo nach wo gezogen wird. Einzige Ausnahme bildet die Umwandlung eines Bauern auf der gegnerischen Grundlinie, da der Spieler selbst entscheidet, in welche Figur er umwandelt (in der Regel, aber nicht zwingend, eine Dame). Rochadezüge werden als Königszüge über zwei Felder in die entsprechende Richtung repräsentiert.

![Ein Zug geht von einem Feld zu einem Feld](/images/Abb09_19_Zug.png "Ein Zug geht von einem Feld zu einem Feld")

*Bild: Ein Zug geht von einem Feld zu einem Feld*

Die Klasse _Stellung_ stellt die aktuelle Situation auf dem Brett dar.
Vor allem sind das die Figuren auf dem Brett, das intern als zweidimensionales Array (8 x 8) implementiert ist.
Falls ein Feld unbesetzt ist, steht null im Array.
Zur Komplettierung der Spielsituation gehört die Information, wer am Zug ist, ob noch Rochaden möglich sind und ob en passant geschlagen werden kann.

![Die Klasse Stellung](/images/Abb09_20_Stellung.png "Die Klasse Stellung \(Ausschnitt, Details wie Rochade fehlen\)")

*Bild: Die Klasse Stellung (Ausschnitt, Details wie Rochade fehlen)*

Die Klasse _Stellung_ ist ebenfalls unveränderlich, die Methode _fuehreZugAus()_ liefert eine neue Stellung mit der veränderten Spielsituation zurück ([→ Entscheidung 9.2 „Sind Stellungsobjekte veränderlich oder nicht?“](/09_entscheidungen/02_stellungsobjekte/)).
