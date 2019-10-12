+++
title = "Eröffnung"
weight = 15
+++

## 5.5 Eröffnung (Blackbox)

### Zweck/Verantwortlichkeit
Dieses Subsystem stellt Eröffnungsbibliotheken bereit und implementiert das Polyglot Opening Book-Format. Bei diesem Format handelt es sich gegenwärtig um das einzig geläufige, das nicht proprietär ist. Entsprechende Buchdateien und zugehörige Werkzeuge sind im Internet frei verfügbar.
Schnittstellen
Das Subsystem stellt seine Funktionalität über das Java-Interface _de.dokchess.eroeffnung.Eroeffnungsbibliothek_ bereit. Als Implementierung liegt die Klasse _de.dokchess.eroeffnung.polyglot.PolyglotOpeningBook_ vor.

![Schnittstelle Eroeffnungsbibliothek, Implementierung PolyglotOpeningBook](/images/Abb09_12_SchnittstellenEroeffnung.png "Schnittstelle Eroeffnungsbibliothek, Implementierung PolyglotOpeningBook")

*Bild: Schnittstelle Eroeffnungsbibliothek, Implementierung PolyglotOpeningBook*

*Tabelle: Methoden der Schnittstelle Eroeffnungsbibliothek*

| Methode | Kurzbeschreibung |
|---------|------------------|
| liefereZug | Liefert zur angegebenen Stellung einen aus der Bibliothek bekannten Zug, oder null |

### PolyglotOpeningBook
Die Klasse PolyglotOpeningBook ist ein Adapter zum Polyglot Opening Book-Dateiformat. Implementierung der Eroeffnungsbibliothek, die eine Binärdatei im entsprechenden Format einliest und einen Zug zur angegebenen Stellung zurückliefert, falls es einen gibt.

*Tabelle: Methoden der Klasse PolyglotOpeningBook (zusätzlich zur Schnittstelle)*

| Methode | Kurzbeschreibung |
|---------|------------------|
| PolyglotOpeningBook | Konstruktor, erwartet die einzulesende Datei.|
| setAuswahlModus | Setzt den Modus zur Auswahl eines Zuges, falls es in der Bibliothek für die Stellung mehr als einen Kandidaten gibt.|

Abschnitt 8.2 beschreibt die in der Schnittstelle verwendeten Aufruf- und Rückgabeparameter (Zug, Stellung).

### Ablageort / Datei
Die Implementierung, Unit-Tests und Testdaten für das Polyglot Opening Book-Fomat liegen unterhalb der Pakete _de.dokchess.eroeffnung..._

### Offene Punkte

* Die Möglichkeiten zur Auswahl eines Zuges aus der Eröffnungsbibliothek im Fall von mehreren Kandidaten sind beschränkt (der erste, der am häufigsten gespielte, per Zufall).
* Die Implementierung kann nicht mit mehreren Bibliotheksdateien zur gleichen Zeit umgehen – sie also nicht mischen – um das Wissen zu vereinen.
