+++
title = "Connection"
pre = "4.4 "
weight = 13
url = "04_solutionstrategy/03_connection"
+++

## 4.4 The Connection of the Engine

DokChess has no graphical user interface.
Instead communication takes place via standard input and output.
The text-based XBoard acts as a communication protocol ([→ Decision 9.1](/en/09_decisions/01_connectivity/) "How does the engine communicate with the outside world?").
You can use DokChess interactively with the command line if you know the XBoard commands and are able to interpret the engine responses ([→ Concept 8.3 User Interface](/en/08_concepts/03_userinterface/)).
See image below:

![DokChess on the command line](/images/en/04_02_DokChess_in_Commandline.png "DokChess on the command line")

The actual DokChess engine is attached by a reactive approach ("Reactive Extensions") ([→ 6.1 Runtime view](/en/06_runtimeview/01_move_determination/) "Move Determination Walkthrough").
DokChess is accessible even during its analysis.
This way, for instance a user can force the engine to move immediately.

On Windows, integrating DokChess in a UI is done with a batch file (_*.bat_).
It starts the Java Virtual Machine (JVM) with the class with the _main_ method as a parameter ([→ 7. 7. Deployment View](/en/07_deploymentview/)).
