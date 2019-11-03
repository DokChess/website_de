+++
title = "Rules"
pre = "5.3 "
weight = 13
url="05_buildingblockview/03_rules"
+++

## 5.3	Subsystem Rules (Blackbox)

### Intent/Responsibility
This subsystem accounts for the rules of chess according to the International Chess Federation (FIDE).
It determines all valid moves for a position and decides whether it is a check, a checkmate or a stalemate.

### Interfaces
The subsystem provides its functionality via the Java interface   
_org.dokchess.rules.ChessRules_.

Default implementation of the interface is class  
_org.dokchess.rules.DefaultChessRules_.

![Interface ChessRules](/images/en/05_Subsystem_Rules.png "Interface ChessRules")
*Fig.: Interface ChessRules*

----

|  Method | Short description |
|-------------------------------|--------------------------------|
| getStartingPosition | Returns the starting position of the game. White begins. |
| getLegalMoves | Returns the set of all legal moves for a given position. The current player is determined from the position parameter. In case of a mate or stalemate an empty collection is the result. Thus the method never returns null. |
| isCheck | Checks whether the king of the given colour is attacked by the opponent. |
| isCheckmate | Checks whether the given position is a mate. I.e. the king of the current player is under attack, and no legal move changes this. The player to move has lost the game. |
| isStalemate | Checks whether the given position is a stalemate. I.e. the current player has no valid move, but the king is not under attack. The game is considered a draw. |
*Table: Methods of interface ChessRules*

----

[→ Concept 8.2 Chess Domain Model](/en/08_concepts/02_domainmodel/) describes the types used in the interface as call and return parameters (_Move_, _Position_, _Colour_).
Refer to the source code documentation (javadoc) for more details.

### Files
The implementation is located below the packages  
_org.dokchess.rules..._

### Open Issues
Apart from the stalemate, the subsystem can not recognize any draw.
In particular, the following rules are not implemented ([→ Risk 11.2](/en/11_risks/02_effort/) "Risk: Effort of implementation"):

* 50 moves rule  
* Threefold repetition
