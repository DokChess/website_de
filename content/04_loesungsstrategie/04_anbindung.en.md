+++
title = "Connection"
pre = "4.4 "
weight = 13
url = "04_solutionstrategy/03_connection"
+++

## 4.4 The Connection of the Engine

DokChess has no graphical user interface.
Instead communication takes place via standard input and output.
The text-based XBoard acts as a communication protocol (→ decision [V.9.1](#section-v-9-1) "How does the engine communicate with the outside world?").
You can use DokChess interactively with the command line if you know the XBoard commands and are able to interpret the engine responses (→ Concept [V.8.3](#section-v-8-3) "User Interface").
See image below:

![DokChess on the command line](/images/en/04_02_DokChess_in_Commandline.png "DokChess on the command line")

The actual DokChess engine is attached by a reactive approach ("Reactive Extensions") (→ Runtime view, [V.6.1](#section-v-6-1) "Move calculation Walkthrough").
DokChess is accessible even during its analysis.
This way, for instance a user can force the engine to move immediately.

On Windows, integrating DokChess in a UI is done with a batch file (_*.bat_).
It starts the Java Virtual Machine (JVM) with the class with the _main_ method as a parameter (→ [V.7](#section-v-7) "Deployment View").
