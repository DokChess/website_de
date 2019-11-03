+++
title = "Evaluation"
pre = "5.8 "
weight = 18
url="05_buildingblockview/08_evaluation"
+++

## 5.8 Evaluation (Blackbox)

### Intent/Responsibility
The module evaluates a position from an opponent's perspective. Result is a number where 0 is a balanced situation.
A positive number describes an advantage for the player, a negative one a drawback.
The higher the number, the greater the advantage or disadvantage.
The module makes it therefore possible to compare positions with each other.

### Interfaces
The _Evaluation_ module provides its functionality via the Java interface  
_org.dokchess.engine.eval.Evaluation_.

The class _org.dokchess.engine.eval.StandardMaterialEvaluation_ is a very simple implementation. The interface contains constants for typical ratings.

![Interface Evaluation and class StandardMaterialEvaluation](/images/en/05_Module_Evaluation.png "Interface Evaluation and class StandardMaterialEvaluation")

*Fig.: Interface Evaluation and class StandardMaterialEvaluation*


|  Method | Short description |
|-------------------------------|--------------------------------|
| evaluatePosition | Returns an evaluation value for the given position from the view of the specified player's colour. The higher the better. |
*Table: Methods of the interface Evaluation*


#### StandardMaterialEvaluation
The implementation class _StandardMaterialEvaluation_ takes only the present pieces (material) into account.
Each piece type has a value (pawn 1, knight 3, ..., queen 9). The pieces on the board are added accordingly.
Own figures are positive, opponent's pieces negative.
Accordingly, with balanced material the result is 0. If you lose a queen, the value drops by 9.


### Files
The implementation is located below the packages   
_org.dokchess.engine.eval..._


### Open Issues
In the pure material evaluation it does not matter where the pieces stand.
A pawn in starting position is worth as much as one short before promotion.
And a knight on the edge corresponds to a knight in the center.
There is plenty of room for improvement, which has not been exploited because DokChess should invite others to experiment.
