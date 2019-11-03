+++
title = "Move Determination"
menuTitle = "6.1 Move Determination"
weight = 11
url="06_runtimeview/01_move_determination"
+++

## 6.1 Move Determination Walkthrough

After establishing the XBoard protocol, the client (white) starts a game by indicating a move.
The following sequence diagram shows an example interaction at the subsystem level from the input "e2e4" (white pawn e2-e4) to DokChess' response, which is the output "move b8c6" (black knight b8-c6, ["Nimzowitsch defense"](https://en.wikipedia.org/wiki/Nimzowitsch_Defence)).

![Sample interaction for move determination](/images/en/06_01_Walkthrough.png "Sample interaction for move determination")
*Fig.: Sample interaction for move determination*

First, the _Text UI_ subsystem validates the input with the aid of the _Rules_ subsystem ([→ Concept 8.4](/en/05_buildingblockview/06_level_2_engine/) "Plausibility Checks and Validation").
The move in the example is recognized as legal and performed on the (stateful) _Engine_ (the _performMove_ message) afterward.
Then, the _Text UI_ subsystem asks the engine to determine its move.
Since move computation can take a long time, but DokChess should still continue to react to inputs, this call is asynchronous. The engine comes back with possible moves.

The _Engine_ examines at first whether the opening book has something to offer.
In the example, this is not the case.
The engine has to calculate the move on its own.
It then accesses the _Rules_ and determines all valid moves as candidates.
Afterward, it investigates and rates them, and gradually reports better moves (better from the perspective of the engine) back to the caller (the _Text UI_ subsystem).
Here, the observer pattern is used (implementation with [reactive extensions](http://reactivex.io/intro.html)).

The example diagram shows that two moves have been found (pawn e7-e5, knight b8-c6) and finally the message, that the search is complete, so the engine does not provide better moves.
The _Text UI_ subsystem takes the last move of the _Engine_ and prints it as a string to standard output according to the XBoard protocol: "move b8c6".
