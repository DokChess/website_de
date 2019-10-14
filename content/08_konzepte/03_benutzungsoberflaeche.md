+++
title = "Benutzungsoberfläche"
weight = 3
+++

## 8.3	Benutzungsoberfläche

DokChess verfügt selbst über keine grafische Oberfläche, sondern agiert über das XBoard-Protokoll mit der Außenwelt ([→ Entscheidung 9.1](/09_entscheidungen/01_anbindung/)). Im Folgenden wird dies kurz skizziert.

Das Protokoll ist textbasiert, ein Starten von DokChess in einer Kommandozeile (Unix-Shell, Windows-Eingabeaufforderung, ...) erlaubt eine Interaktion mit der Engine, wenn man die wichtigsten XBoard-Kommandos beherrscht (siehe Bild in [Abschnitt 4](/04_loesungsstrategie/)).
Die folgende Tabelle zeigt einen Beispieldialog, alle Kommandos werden mit einer neuen Zeile abgeschlossen). Standardmäßig spielt eine Engine schwarz, man kann das über die Protokollbefehl "white" ändern.

*Tabelle: Beispielkommunikation zwischen einem Client und DokChess (XBoard)*

| Client -> DokChess | DokChess -> Client | Bemerkung |
|--------------------|--------------------|-----------|
| _xboard_           | &nbsp;             | Client will XBoard-Protokoll verwenden (erforderlich, da Engines teilweise andere, teileweise sogar mehrere Protokolle verstehen) |
| &nbsp;             | (neue Zeile)       | &nbsp; |
| _protover 2_       | &nbsp;             |	Protokollversion 2 |
| &nbsp;             | _feature done=1_   | zeilenweise Mitteilung über zusätzliche Features der Engine (hier: keine) |
| _e2e4_             | &nbsp;             | Weiß zieht Bauer e2-e4 |
| &nbsp;             | _move b8c6_        | Schwarz (DokChess) zieht Springer b8-c6 |
| _quit_             | &nbsp;             | Der Client beendet das Spiel (DokChess terminiert) |

Das Protokoll selbst wird in [Mann+2009] detailliert beschrieben, für die Implementierung in DokChess ist das Subsystem XBoard-Protokoll zuständig ([→ Bausteinsicht 5.2](/05_bausteinsicht/02_xboard-protokoll/)).

Die typische Verwendung von DokChess ist das Vorschalten eines grafischen Schachfrontends wie Arena (siehe Bild unten), das die Züge des Gegners über eine komfortable Oberfläche entgegennimmt und diese in Form von XBoard-Kommandos wie in der Tabelle oben an DokChess weitergibt (Spalte "Client -> DokChess") und die Antworten (Spalte "DokChess -> Client") grafisch umsetzt.

![DokChess im Schach-Frontend Arena unter Windows](/images/Abb09_21_FrontendArena.png "DokChess im Schach-Frontend Arena unter Windows")

*Bild: DokChess im Schach-Frontend Arena unter Windows*
