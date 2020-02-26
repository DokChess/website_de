+++
title = "Game Strategy"
pre = "4.3 "
weight = 12
url = "04_solutionstrategy/02_gamestrategy"
+++

## 4.3 Game Strategy

For the integration of opening libraries, the "Polyglot Opening Book" file format was implemented ([→ Building Block View 5.5](/en/05_buildingblockview/05_opening/) "Subsystem Opening (Blackbox)").
This way, DokChess responds with profound chess knowledge in the beginning of a game.

The classic [minimax algorithm](https://en.wikipedia.org/wiki/Minimax) with a fixed search depth in the game tree is responsible for the strategy as the game continues.
Its basic implementation is single-threaded.
The evaluation of a position at an end node in the game tree is based solely on the material ([→ 5.6 Building Block View, Level 2](/en/05_buildingblockview/06_level_2_engine/) "Engine (Whitebox)").
Nevertheless, these simple implementations already meet the quality scenarios under the given constraints.

An [alpha-beta pruning](https://en.wikipedia.org/wiki/Alpha–beta_pruning) illustrates the simple replacement of algorithms.
Playing strength and efficiency considerably improve by searching the tree more deeply within the same computation time.
The immutable data structures of DokChess also facilitate implementing concurrent algorithms; a parallel minimax algorithm is included as an example.
