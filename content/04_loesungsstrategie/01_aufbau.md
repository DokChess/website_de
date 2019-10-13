+++
title = "Aufbau"
weight = 11
+++

## 4.1 Der Aufbau von DokChess

DokChess ist als Java-Programm mit main-Routine realisiert. Es zerfällt grob in folgende Teile:

* eine Implementierung der Schachregeln
* die eigentliche Engine, welche die Züge ermittelt
* die Anbindung an eine grafische Benutzeroberfläche über das XBoard-Protokoll
* einen Adapter für ein konkretes Eröffnungsbibliotheksformat (Polyglot Opening Book)

Diese Zerlegung ermöglicht es, Dinge wie das Kommunikationsprotokoll oder das Eröffnungsbibliotheksformat bei Bedarf auszutauschen. Alle Teile sind durch Schnittstellen abstrahiert, die Implementierungen werden per Dependency Injection zusammengesteckt ([→ 5. Bausteinsicht](/05_bausteinsicht/), [→ Konzept 8.1 „Abhängigkeiten zwischen Modulen"](/08_konzepte/01_abhaengigkeiten/).
Die Zerlegung erlaubt es weiterhin die Software, allen voran die Schachalgorithmen, leicht automatisiert zu testen ([→ Konzept 8.7 „Testbarkeit“](/08_konzepte/07_testbarkeit/)).

Die Interaktion zwischen Algorithmen­Teilen erfolgt über den Austausch fachlich motivierter Datenstrukturen, realisiert als Klassen (_Figur_, _Zug_, ... [→ Konzept 8.2 „Schach­Domänenmodell“](/08_konzepte/02_domaenenmodell/)).
Hier wurde bewusst eine bessere Verständlichkeit angestrebt, auf Kosten von Effizienz.
Gleichwohl erreicht DokChess eine akzeptable Spielstärke, wie ein Durchspielen der entsprechenden Szenarien zeigt ([→ 10. Qualitätsszenarien](/10_qualitaetsszenarien/)).

Zentrales Element beim Entwurf der Datenstrukturen ist die Spielsituation: Welche Figuren gerade wo stehen und was sonst noch zur Stellung dazu gehört (z. B. wer am Zug ist).
Auch hier ging bei der Implementierung der fachlich motivierten Klasse dazu Lesbarkeit vor Effizienz.
Ein wichtiger Aspekt dabei: Wie alle anderen fachlichen Klassen ist auch sie unveränderlich ([→ Entscheidung 9.2 „Sind Stellungsobjekte veränderlich oder nicht?“](/09_entscheidungen/02_stellungsobjekte/)).
