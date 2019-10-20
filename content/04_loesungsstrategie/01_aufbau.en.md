+++
title = "Structure"
weight = 11
url = "04_solutionstrategy/01_structure"
+++

## 4.1 Structure of DokChess

DokChess is implemented as a Java program with a main routine. It is roughly split into the following parts:

* An implementation of the rules of chess
* The engine itself, which selects the moves
* The connection to a graphical user interface via the XBoard protocol
* An adapter for a specific opening book format (Polyglot Opening Book)

This decomposition allows you to replace things such as the communication protocol or the opening book format if necessary.
All parts are abstracted through interfaces.
Their implementations are assembled via dependency injection (→ [V.5](#section-v-5) "Building Block View", → Concept [V.8.1](#section-v-8-1) "Dependencies Between Modules").
The decomposition further allows the software, especially the chess algorithms, to be tested automatically. (→ Concept [V.8.7](#section-v-8-7) "Testability").

The interaction between algorithms takes place using the exchange of data structures motivated by the domain implemented as Java classes (piece, move and so on → Concept [V.8.2](#section-v-8-2) "Chess Domain Model").
Here, better understandability is preferred at the cost of efficiency.
Nevertheless, DokChess reached an acceptable playing strength, as a run through the corresponding scenarios shows ([→ 10. "Quality Scenarios"](/en/10_qualityscenarios/)).

The key element of the data structure design is the game situation.
This includes the placement of the chess pieces and other aspects that belong to the position (such as which side moves next).
Again readability is preferred to efficiency in the implementation of the class motivated by the domain.
An important aspect is that, like all other domain classes this class is immutable (→ decision [V.9.2](#section-v-9-2) "Are position objects changeable or not?").
