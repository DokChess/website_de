+++
title = "DokChess"
+++

# DokChess als Beispiel für arc42

Diese Seiten beschreiben die Architektur des Schach-Programmes DokChess.
Ich habe es als Anschauungsmaterial für Vorträge und Seminare rund um Softwarearchitektur und -entwurf konzipiert und implementiert.
Es dient als Fallbeispiel in meinem Buch über Architekturdokumentation.

### Architekturüberblick DokChess

Dieser Architekturüberblick lässt Sie die maßgeblichen Entwurfsentscheidungen nachvollziehen.
Er zeigt die Struktur der Lösung und das Zusammenspiel zentraler Elemente.
Die Gliederung der Inhalte erfolgt nach der arc42-Vorlage.
Zielgruppe dieses Überblicks sind in erster Linie Softwarearchitekten, die Anregungen und Beispiele suchen, wie man Architekturentwürfe angemessen dokumentieren kann.
Entwickler, die selbst ein Schachprogramm schreiben wollen, erhalten wertvolle Tipps und lernen en passant einiges über methodische Softwarearchitektur.

----------------

### arc42 Reference

We acknowledge that this document uses material from the arc 42 architecture template, http://www.arc42.de. Created by Dr. Peter Hruschka & Dr. Gernot Starke.
