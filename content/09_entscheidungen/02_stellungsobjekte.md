+++
title = "Stellungsobjekte"
weight = 2
+++

## 9.2 Sind Stellungsobjekte veränderlich oder nicht?

### Zur Fragestellung

Spielsituationen auf dem Schachbrett (Stellungen) müssen für verschiedene DokChess-Module bereitgestellt und zwischen ihnen ausgetauscht werden. Gestalten wir die zugehörige Datenstruktur veränderlich oder unveränderlich (immutable)?

Eine Stellung verändert sich im Verlauf einer Partie durch das Ausführen von Zügen. Darüber hinaus führt die Engine im Rahmen ihrer Analyse mögliche Züge aus, zieht Antworten des Gegners, bewertet das Resultat und verwirft Züge wieder. Dabei entsteht ein Baum, der je nach Tiefe viele tausend verschiedene Stellungen beinhaltet.

Je nachdem, ob die Stellung als Datenstruktur unveränderlich ist oder nicht, sind Algorithmen einfacher oder schwieriger zu implementieren, und ihre Ausführung ist unterschiedlich effizient.

Von der Schnittstelle der Stellung hängen sämtliche Module ab; eine nachträgliche Änderung beträfe ganz DokChess.

### Relevante Einflussfaktoren

* Randbedingungen (→ 2.1 „Technische Randbedingungen“)
 * Implementierungssprache Java
 * moderate Hardwareausstattung
* Maßgeblich betroffene Qualitätsmerkmale (→ 1.2 „Qualitätsziele“)
 * Qualitätsziel: Einladende Experimentierplattform (Änderbarkeit)
 * Qualitätsziel: Akzeptable Spielstärke (Attraktivität)
 * Qualitätsziel: Schnelles Antworten auf Züge (Effizienz)
* Betroffene Risiken
 * Aufwand der Implementierung (→ 11.2)
 * Erreichen der Spielstärke (→ 11.3)

### Annahmen

* Es ist möglich, eine Datenstruktur mit ausformuliertem Objektmodell (also Klassen Feld, Figur, Zug etc.) effizient genug zu implementieren, um die geforderte Spielstärke bei angemessener Antwortzeit zu liefern.
* In Zukunft sollen mit der Datenstruktur auch nebenläufige Algorithmen realisiert werden können.

### Betrachtete Alternativen

Ausgangspunkt sind fachlich motivierte Klassen für Feld, Figur und Zug (→ 8.2 „Schach-Domänenmodell“). Die Klassen sind unveränderlich als Wertobjekte realisiert (Feld e4 bleibt nach Erzeugung stets e4).
Für die Stellung werden zwei Alternativen betrachtet:

* Option (1): Die Stellung ist veränderlich. Einzelne Methoden der Schnittstelle verändern den Zustand, führen beispielsweise Züge aus oder nehmen sie zurück.

<pre>// Pseudocode
Stellung s = new Stellung(); // Anfangsstellung, weiss am Zug
s.fuehreZugAus(e2e4);        // Koenigsbauer zwei Felder vor, danach schwarz am Zug
s.nimmLetztenZugZurueck();   // anschliessend wieder auf Anfang
...
</pre>

* Option (2): Die Stellung ist unveränderlich ("immutable"), d.h. eine Methode zum Ausführen eines Zuges liefert die neue Stellung (Kopie der alten, anschließend Zug ausgeführt) als ebenfalls unveränderliches Objekt zurück.

<pre>Stellung s = new Stellung();
Stellung neueStellung = s.fuehreZugAus(e2e4) // s bleibt unveraendert
...
</pre>

Die folgende Tabelle fasst Stärken und Schwächen der beiden Optionen zusammen, sie werden im Folgenden weiter ausgeführt.

*Tabelle: Stärken und Schwächen der beiden Optionen*

| &nbsp;          | (1) veränderlich | (2) unveränderlich  |
|-----------------|------------------|---------------------|
| Implementierungsaufwand | (-) höher | (+) geringer |
| Effizienz (Speicherverbrauch) | (+) sparsamer | (-) Bedarf höher |
| Effizienz (Zeitverhalten) | (o) neutral | (-) schlechter |
| Eignung für nebenläufige Algorithmen | (-) schlecht | (+) gut |

#### Option (1): Veränderliche Stellung

(+) Positiv

Die Stellung mit ihrem umfangreichen Zustand muss nicht bei jedem Zug kopiert werden. Das spart Speicher und Rechenzeit, und es schont den Garbage Collector. Für Analysealgorithmen ist allerdings Funktionalität zu implementieren, die ausgeführte Züge zurücknimmt („undo“). Dieses Zurücknehmen kostet ebenfalls Zeit, daher die neutrale Bewertung (o) beim Zeitverhalten.

(-) Negativ

Die Implementierung des Zurücknehmens ist aufwändig, es müssen nicht nur geschlagene Figuren wieder hingestellt werden. Die Rochade-Regel und En passant erfordern eine gesonderte Behandlung. Das Command-Pattern [Gamma+94] bietet sich als Option an. Auch die Verwendung durch Algorithmen ist aufwändiger, da diese das Zurücknehmen von Zügen explizit aufrufen müssen.

Veränderbarer Zustand hat Nachteile bezüglich Nebenläufigkeit.

#### Option (2): Unveränderliche Stellung

(+) Positiv

Beim Ausführen eines Zuges wird die Stellung kopiert, das Original nicht verändert. Damit entfällt die Implementierung des Zurücknehmens von Zügen. Verwender können sich die alte Stellung als Wert merken. Das spart verglichen mit Option (1) Aufwand in der Umsetzung.
Unveränderliche Objekte bieten signifikante Vorteile bei nebenläufigen Algorithmen.

(-) Negativ
Das Kopieren des Zustandes für jede neue Stellung kostet Zeit. Da es in Analysesituationen um sehr viele Stellungen geht, in Summe potentiell viel Zeit.

Das Kopieren des Zustandes für jede neue Stellung kostet darüber hinaus Speicher. Die Implementierung von Suchalgorithmen mit Backtracking vermeidet zwar, dass komplette Spielbäume auf dem Heap landen. Nichts desto trotz ist der Speicherbedarf höher, und der Garbage Collector hat viel mehr zu tun.

Beide Punkte wirken sich negativ auf die Effizienz aus.

### Entscheidung

Die Entscheidung fiel Anfang 2011 auf die unveränderliche Stellung (Option 2) aufgrund der Vorteile bezüglich einfacher Implementierung und Aussicht auf die leichtere Ausnutzung von Nebenläufigkeit. Die Nachteile der Option 2 beziehen sich ausschließlich auf Effizienz.

Aufgrund des Risikos, die Ziele bezüglich der Spielstärke in akzeptabler Rechenzeit (Attraktivität, Effizienz) nicht zu erreichen, wurden Prototypen beider Varianten implementiert und im Rahmen einer Mattsuche (Matt in 3 Zügen) mit Minimax-Algorithmus verglichen. Mit Option 2 dauerte die Suche 30% länger, vorausgesetzt, man implementiert das Kopieren effizient. Sie lag aber noch deutlich innerhalb des Geforderten.

Es gab weitere Optimierungsoptionen, die den Effizienznachteil gegenüber Option (1) bei Bedarf weiter verkürzt hätten. Sie wurden nicht umgesetzt, um die Implementierung einfach zu halten.

Zu diesen Optionen zählte die Ausnutzung mehrerer Prozessoren/Kerne durch Nebenläufigkeit, mittlerweile (mit DokChess 2.0) mit einem parallelen Minimax exemplarisch umgesetzt.
