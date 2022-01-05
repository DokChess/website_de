+++
title = "Structure"
pre = "4.2 "
weight = 11
url = "04_solutionstrategy/02_structure"
+++

## 4.2 Structure of DokChess

DokChess is implemented as a Java program with a main routine. It is roughly split into the following parts:

* An implementation of the rules of chess
* The engine itself, which selects the moves
* The connection to a graphical user interface via the XBoard protocol
* An adapter for a specific opening book format (Polyglot Opening Book)

This decomposition allows you to replace things such as the communication protocol or the opening book format if necessary.
All parts are abstracted through interfaces.
Their implementations are assembled via dependency injection ([→ 5. Building Block View](/en/05_buildingblockview/), [→ 8.1 Dependencies Between Modules](/en/08_concepts/01_dependencies/)).
The decomposition further allows the software, especially the chess algorithms, to be tested automatically. ([→ 8.7 Testability](/en/08_concepts/07_testability/)).

The interaction between algorithms takes place using the exchange of data structures motivated by the domain implemented as Java classes (piece, move and so on, [→ 8.2 Chess Domain Model](/en/08_concepts/02_domainmodel/)).
Here, better understandability is preferred at the cost of efficiency.
Nevertheless, DokChess reached an acceptable playing strength, as a run through the corresponding scenarios shows ([→ 10. Quality Scenarios](/en/10_qualityrequirements/)).

The key element of the data structure design is the game situation.
This includes the placement of the chess pieces and other aspects that belong to the position (such as which side moves next).
Again readability is preferred to efficiency in the implementation of the class motivated by the domain.
An important aspect is that, like all other domain classes this class is immutable ([→ Decision 9.2](/en/09_decisions/02_positionobjects/) "Are position objects changeable or not?").
