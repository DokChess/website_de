+++
title = "Anbindung"
weight = 15
+++

## 9.1 Wie kommuniziert die Engine mit der Außenwelt?

### Zur Fragestellung

Als zentrale Anforderung muss DokChess mit vorhandenen Schach-Frontends zusammenarbeiten. Wie erfolgt die Anbindung?

Es sind eine ganze Reihe grafische Oberflächen speziell zum Spiel gegen Schach-Programme verfügbar. Darüber hinaus gibt es für Schachinteressierte Softwarelösungen mit größerem Leistungsumfang. Neben dem Spiel „Mensch gegen Maschine“ bieten sie weitere Funktionalität, etwa zur Analyse von Partien. Mit der Zeit werden neue Schach-Programme hinzukommen – und andere gegebenenfalls vom Markt verschwinden.

Je nachdem, wie die Anbindung an solche Programme realisiert wird, kann DokChess mit bestimmten Oberflächen kommunizieren oder auch nicht. Die Frage hat Einfluss auf die Interoperabilität von DokChess mit bestehender und auf die Anpassbarkeit an zukünftige Schach-Software.

### Relevante Einflussfaktoren

* Randbedingungen
 * Betrieb der Frontends zumindest auf Windows-Desktop-Betriebssystemen
 * Unterstützung frei verfügbarer Frontends
 * Bevorzugung etablierter (Schach-)Standards (→ 2.3 „Konventionen“)
* Maßgeblich betroffene Qualitätsmerkmale (→ 1.2 „Qualitätsziele“)
 * Qualitätsziel: Bestehende Frontends nutzen (Interoperabilität)
 * Qualitätsziel: Einladende Experimentierplattform (Änderbarkeit)
 * Anpassbarkeit (an zukünftige Schach-Software)
* Betroffene Risiken
 * Anbindung an das Frontend (→ 11.1)

### Annahmen

* Die Untersuchung weniger verfügbarer Frontends führt zu allen interessanten Integrationsoptionen.

### Betrachtete Alternativen

Anfang 2011 wurden folgende Schach-Frontends untersucht:

* Arena Chess GUI (frei verfügbar, läuft unter Windows)
* Fritz for Fun (kommerziell, Anbieter ChessBase GmbH, läuft unter Windows)
* Winboard/XBoard (Open Source, läuft unter Windows, Max OS X, *nix)

Als Ergebnis wurden zwei Kommunikationsprotokolle als Optionen identifiziert:

* Option 1: UCI Protocol (Universal Chess Interface), siehe [MeyerKahlen2004]
* Option 2: XBoard Protocol (auch bekannt als Winboard, und als Chess Engine Communication Protocol), siehe [Mann+2009]

Keines der beiden Protokolle ist formal spezifiziert, aber beide sind öffentlich dokumentiert.

Beide Protokolle sind textbasiert, die Kommunikation zwischen Frontend und Engine erfolgt über stdin/stdout. Das Frontend startet die Engine jeweils in einem separaten Prozess.

Die folgende Tabelle zeigt, welches der untersuchten Frontend welches Protokoll implementiert.

*Tabelle: Protokolle und Frontends*

| &nbsp;           | Arena 3 | Fritz for Fun | Winboard/XBoard |
|------------------|---------|---------------|-----------------|
| UCI-Protokoll    | Ja      | Ja            | \-              |
| XBoard-Protokoll | Ja      | \-            | Ja              |

### Entscheidung

Grundsätzlich lassen sich die Qualitätsziele unter den gegebenen Randbedingungen von beiden Protokollen erreichen. Je nachdem, welches Protokoll implementiert wird, werden unterschiedliche Frontends unterstützt.

Die Entscheidung fiel Anfang 2011 zugunsten des XBoard-Protokolls. Die Struktur von DokChess erlaubt es, alternative Kommunikationsprotokolle (UCI oder andere) hinzuzufügen, ohne die Engine selbst dafür verändern zu müssen, siehe hierzu Abhängigkeiten in der Bausteinsicht (→ 5.1).
Das präferierte Frontend unter Windows ist Arena. Es ist frei verfügbar und vom Leistungsumfang WinBoard überlegen. Es besitzt gute Debug-Möglichkeiten, kann zum Beispiel die Kommunikation zwischen Frontend und Engine live in einem Fenster darstellen (siehe Bild 9.23). Arena unterstützt beide Protokolle.

Mit der Entscheidung für das XBoard-Protokoll werden zusätzlich zu Windows weitere Betriebssysteme (insbesondere Mac OS X und Linux) mit einem frei verfügbaren Frontend unterstützt. Da so ein größerer Kreis Interessierter die Engine verwenden kann, gab dies letztendlich den Ausschlag.
