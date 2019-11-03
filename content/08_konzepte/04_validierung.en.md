+++
title = "Validation"
menuTitle = "8.4 Validation"
weight = 4
url="08_concepts/04_validation"
+++

## 8.4 Plausibility Checks and Validation

In simple terms, DokChess is an algorithm. It responds to moves of the opponent with its own moves. Two channels are relevant for input validation:

* the XBoard protocol for interactive user input from the opponent
* opening libraries in the form of files

Input that comes through the XBoard protocol is parsed from the corresponding subsystem. In case of unknown or unimplemented commands DokChess reports the XBoard command "Error" back to the client.

In case of move commands DokChess checks using the rules subsystem whether the move is allowed or not. In case of illegal moves DokChess reports the XBoard command "Illegal move" back to the client. When using a graphical front end, this case should not occur, since these typically accept only valid moves. The case is likely relevant when interacting via command line ([→ 8.3 User Interface](/en/08_concepts/03_userinterface/)).

Inputs that come through the XBoard protocol are parsed from the corresponding subsystem. For unknown or unimplemented commands DokChess reports the XBoard command "Error" back to the client. When setting up a position DokChess checks the compliance with the protocol, but not whether the position is permitted. In extreme cases (e.g. if no kings are present on the board), the engine subsystem may raise an error during the game.

For opening libraries DokChess only checks whether it can open and read the file.
In case of a failure (e.g. file not found) it raises an exception ([→ 8.5 Exception and Error Handling](/en/08_concepts/05_errorhandling/)) "Exception and Error Handling").
While reading the file the opening subsystem responds with a runtime error to recognized problems (for example, invalid file format). However, the content of the library itself is not checked. For example, if invalid moves are stored for a position it is not recognized. The user is responsible for the quality of the library (see [→ 3. Context](/en/03_context/).
In extreme cases, the engine may respond with an illegal move.
