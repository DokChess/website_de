+++
title = "Evaluation Scenarios"
weight = 2
url="10_qualityscenarios/02_evaluationscenarios"
+++

## 10.2 Evaluation Scenarios

|No.| Scenario                                          |
|-----|--------------------|
| 1 | A person with basic knowledge of UML and chess looks for an introduction to the DokChess architecture. He or she gets the idea of the solution strategy and the essential design within 15 minutes.                                           |
| 2 | An architect who wishes to apply arc42 searches for a concrete example for an arbitrary section of the template. He or she finds the relevant content immediately in the documentation.                                           |
| 3 | An experienced Java developer searches for the implementation of a module described in the design. He or she finds it in the source code without detours or help from others.                                           |
| 4 | A developer implements a new position evaluation. He or she integrates it into the existing strategies without modification and without compilation of existing source code.                                           |
| 5 | A developer implements a piece-centric bitboard representation of the game situation. The effort (which includes replacing the existing, square-centric representation) is lower than one person week.                                           |
| 6 | A weak player is in a game against the engine. The player moves a piece to an unguarded position which is being attacked by the engine. The engine consequently takes the dropped piece.                                           |
| 7 | Within a chess match, a mate in two unfolds to the engine. The engine moves safely to win the game.                                           |
| 8 | Within a chess match, a knight fork to gain the queen or a rook arises for the engine. The engine gains the queen (or the rook) in exchange for the knight.                                         |
| 9 | In a game situation, the engine has one or more rule-compliant moves to choose from. It plays one of them.                                         |
|10 | During the game, the engine responds to the move of the opponent with its own move within 5 seconds.                                         |
|11 | An engine integrated in a graphical frontend plays as black, and the human player begins. The engine responds within 10 seconds with its first move, and the user gets a message that the engine "thinks" within 5 seconds.                                         |
|12 | A user plans to use DokChess with a frontend that supports a communication protocol that's already implemented by the solution. The integration does not require any programming effort, the configuration with the front end is carried out and tested within 10 minutes.                                         |
|13 | A Java programmer plans to use a chess frontend that allows the integration of engines, but does not support any of the protocols implemented by DokChess. The new protocol can be implemented without changing the existing code, and the engine can then be integrated as usual.                                         |
|14 | During the game, the engine receives an invalid move. The engine rejects this move and allows the input of another move thereafter and plays on in an error-free way.                                         |
|15 | The engine receives an illegal position to start the game. The behavior of the engine is undefined, cancelling of the game is allowed, as well as invalid moves.                                         |
