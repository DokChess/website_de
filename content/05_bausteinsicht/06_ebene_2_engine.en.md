+++
title = "Level 2: Engine"
pre = "5.6 "
weight = 16
url="05_buildingblockview/06_level_2_engine"
+++

## 5.6 Level 2: Engine (Whitebox)

The engine breaks down in modules _Search_ and (position) _Evaluation_ as shown in the following diagram.
If available, the determination of the move is initially delegated to an opening book.
Only if the book does not provide a standard move _Search_ is used.

![Engine, building block view, level 2](/images/en/05_Engine_Level_2.png "Engine, building block view, level 2")
*Fig.: Engine, building block view, level 2*

----

|  Module | Short description |
|-------------------------------|--------------------------------|
| [Search](/en/05_buildingblockview/07_search/)   | Determines the optimal move for a position under certain conditions. |
| [Evaluation](/en/05_buildingblockview/08_evaluation/) | Evaluates a position from an opponent's perspective.|
*Table: Modules of Engine subsystem*
