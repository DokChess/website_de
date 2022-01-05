---
title: "Quality Scenarios"
pre: "10.2 "
weight: 2
url: "10_qualityrequirements/02_qualityscenarios"
---

## 10.2 Quality Scenarios

The initial letters of the identifiers (IDs) of the scenarios in the following table each stand for the parent quality attribute (in German), E for efficiency, for instance.
These identifiers are also used in the [quality tree](/en/10_qualityrequirements/01_utilitytree/).
The scenarios cannot always be clearly assigned to one characteristic.
Therefore, they sometimes appear several times in the quality tree.

| ID | Scenario           |
|-----|--------------------|
| W01 | A person with basic knowledge of UML and chess looks for an introduction to the DokChess architecture. He or she gets the idea of the solution strategy and the essential design within 15 minutes |
| W02 | An architect who wishes to apply arc42 searches for a concrete example for an arbitrary section of the template. He or she finds the relevant content immediately in the documentation.|
| W03 | An experienced Java developer searches for the implementation of a module described in the design. He or she finds it in the source code without detours or help from others. |
| W04 | A developer implements a new position evaluation. He or she integrates it into the existing strategies without modification and without compilation of existing source code. |
| W05 | A developer implements a piece-centric bitboard representation of the game situation. The effort (which includes replacing the existing, square-centric representation) is lower than one person week. |
| K01 |  A user plans to use DokChess with a frontend that supports a communication protocol that's already implemented by the solution. The integration does not require any programming effort, the configuration with the front end is carried out and tested within 10 minutes. |
| F01 | In a game situation, the engine has one or more rule-compliant moves to choose from. It plays one of them. |
| F02 | A weak player is in a game against the engine. The player moves a piece to an unguarded position which is being attacked by the engine. The engine consequently takes the dropped piece. |
| F03 | Within a chess match, a knight fork to gain the queen or a rook arises for the engine. The engine gains the queen (or the rook) in exchange for the knight. |
| F04 | Within a chess match, a mate in two unfolds to the engine. The engine moves safely to win the game. |
| E01 | During the game, the engine responds to the move of the opponent with its own move within 5 seconds. |
| E02 |An engine integrated in a graphical frontend plays as black, and the human player begins. The engine responds within 10 seconds with its first move, and the user gets a message that the engine "thinks" within 5 seconds. |
| Z01 | During the game, the engine receives an invalid move. The engine rejects this move and allows the input of another move thereafter and plays on in an error-free way. |
| Z02 | The engine receives an illegal position to start the game. The engine recognizes the situation and quits the game. |
| P01 | A Java programmer plans to use a chess frontend that allows the integration of engines, but does not support any of the protocols implemented by DokChess. The new protocol can be implemented without changing the existing code, and the engine can then be integrated as usual. |
