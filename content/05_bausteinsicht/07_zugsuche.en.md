+++
title = "Search"
pre = "5.7 "
weight = 17
url="05_buildingblockview/07_search"
+++

## 5.7 Search (Blackbox)


### Intent/Responsibility
The module determines the optimal move for a position under certain conditions.
In the game of chess an optimal move always exists, theoretically.
The high number of possible moves and the resulting incredible mass of game situations to consider makes it impossible to determine it in practice.
Common algorithms like the Minimax therefore explore the "game tree" only up to a certain depth.


### Interfaces
The module provides its functionality via the Java interface   
_org.dokchess.engine.search.Search_.

Class _org.dokchess.engine.search.MinimaxAlgorithm_ implements the interface with the Minimax algorithm.
The class _MinimaxParallelSearch_ uses the algorithm and implements the same interface _Search_.
It examines several subtrees concurrently; if it finds a better move the caller receives a message _onNext_ via the observer pattern.
The search indicates the completion of its work with the message _onComplete_.

![Interface Search, classes MinimaxAlgorithm and MinimaxParallelSearch](/images/en/05_Module_Search.png "Interface Search, classes MinimaxAlgorithm and MinimaxParallelSearch")

*Fig.: Interface Search, classes MinimaxAlgorithm and MinimaxParallelSearch*


|  Method | Short description |
|-------------------------------|--------------------------------|
| searchMove | Starts a search for a move on the specified position. Returns gradually better moves as events on the passed observer. The end of the search (no better move found) is also signaled to the observer. |
| cancelSearch | Cancels the current search. |
| close | Closes the search completely. No moves may be determined after calling this method. |
*Table: Methoden der Schnittstelle Suche*


|  Method | Short description |
|-------------------------------|--------------------------------|
| setEvaluation | Set the evaluation function on which the positions are rated when the maximum search depth is reached. [→ Module Evaluation (Black Box)](/en/05_buildingblockview/08_evaluation/) |
| setChessRules | Sets an implementation of the chess rules via dependency injection, [→ Subsystem Rules (Black Box)](/en/05_buildingblockview/03_rules/) |
| setDepth | Set the maximum search depth in half moves. That means at 4 each player moves twice. |
| determineBestMove | Determines the optimal move according to minimax for the position passed and given evaluation at fixed search depth. The method blocks and is deterministic. |
*Table: Methods of the class MinimaxAlgorithm*


### Files
The implementation is located below the packages   
_org.dokchess.engine.search..._
