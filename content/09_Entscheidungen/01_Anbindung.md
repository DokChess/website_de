+++
title = "Anbindung"
weight = 15
+++

## Wie kommuniziert die Engine mit der Außenwelt?

### Zur Fragestellung

Als zentrale Anforderung muss DokChess mit vorhandenen Schach-Frontends zusammenarbeiten.
Wie erfolgt die Anbindung?

Als zentrale Anforderung muss DokChess mit vorhandenen Schach-Frontends zusammenarbeiten. Wie erfolgt die Anbindung?

Es sind eine ganze Reihe grafische Oberflächen speziell zum Spiel gegen Schach-Programme verfügbar. Darüber hinaus gibt es für Schachinteressierte Softwarelösungen mit größerem Leistungsumfang. Neben dem Spiel „Mensch gegen Maschine“ bieten sie weitere Funktionalität, etwa zur Analyse von Partien. Mit der Zeit werden neue Schach-Programme hinzukommen – und andere gegebenenfalls vom Markt verschwinden.

Je nachdem, wie die Anbindung an solche Programme realisiert wird, kann DokChess mit bestimmten Oberflächen kommunizieren oder auch nicht.
Die Frage hat Einfluss auf die Interoperabilität von DokChess mit bestehender und auf die Anpassbarkeit an zukünftige Schach-Software.

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
