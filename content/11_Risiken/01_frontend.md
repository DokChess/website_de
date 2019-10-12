+++
title = "Frontend"
weight = 1
+++

## 11.1 Risiko: Anbindung an das Frontend
Es liegt keinerlei Wissen über die Anbindung einer Engine an ein vorhandenes Schach-Frontend vor. Vorhandene Open Source Engines sind in C programmiert und werden als ausführbare Programme (\*.exe) geliefert. Da DokChess in Java entwickelt wird, taugen sie nur bedingt zur Inspiration. Über Kommunikationsprotokolle ist überhaupt nichts bekannt.

Falls es nicht gelingt, eine funktionierende Anbindung zu realisieren, kann die Lösung nicht mit bestehenden Frontends verwendet werden. Damit fehlt nicht nur ein wichtiges Feature (vgl. Aufgabenstellung), sondern die Lösung ist als Ganzes, insbesondere auch als Fallbeispiel, unglaubwürdig.

### Eventualfallplanung
Es könnte ein einfaches textuelles User Interface realisiert werden, um mit der Engine zu interagieren. Aufwändiger wäre die Implementierung eines eigenen grafischen Frontends (siehe auch Risiko 11.2).

### Risikominderung
Durch einen Proof of concept wird hier frühestmöglich Sicherheit erreicht.
