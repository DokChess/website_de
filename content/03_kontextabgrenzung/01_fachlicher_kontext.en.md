+++
title = "Business Context"
menuTitle = "3.1 Business Context"
weight = 1
url = "03_context/01_business"
+++

## 3.1 Business Context

![Business Context of DokChess](/images/en/03_01_BusinessContext.png "Business Context of DokChess")
##### Fig.: Business Context of DokChess

-----

#### Human opponent (user)
Chess is played between two opponents, who move their pieces in turn.
DokChess takes the role of one of the opponents, and competes against a human opponent.
For this purpose, the two need to communicate, e.g. about their moves, or draw offers.

#### Computer opponent (external system)
As an alternative to a human opponent DokChess can also compete with a different engine.
The requirements related to the exchange of information are the same.

#### Openings (external system)
About the opening, which is the early stage of a game, extensive knowledge exists in chess literature.
This knowledge is partly free and partly also commercially available in the form of libraries and databases.
Within DokChess no such library is created.
Optionally an external system is connected instead in order to permit a knowledge based play in the early stages, as expected by human players.

#### Endgames (external system)
If just a very few pieces are left on the board (e.g. only the two kings and a queen), endgame libraries can be used analogously to opening libraries.
For any position with this piece constellation these libraries include the statement whether a position is won, drawn or lost, and if possible the necessary winning move.

Within DokChess no such library is created. Optionally an external system is connected instead in order to bring clearly won games home safely, or to use the knowledge from the libraries for analysis and position evaluation.
