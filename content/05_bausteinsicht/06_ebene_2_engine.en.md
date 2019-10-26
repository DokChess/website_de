+++
title = "Level 2: Engine"
weight = 16
url="05_buildingblockview/06_level_2_engine"
+++

## 5.6 Level 2: Engine (Whitebox)

The engine breaks down in modules _Search_ and (position) _Evaluation_ as shown in the following diagram.
If available, the determination of the move is initially delegated to an opening book.
Only if the book does not provide a standard move _Search_ is used.

![Engine, building block view, level 2](/images/en/05_Engine_Level_2.png "Engine, building block view, level 2")

*Fig.: Engine, building block view, level 2*

*Table: Modules of Engine subsystem*

|  Module | Short description |
|-------------------------------|--------------------------------|
| [Search](#section-v-5-2-1)   | Determines the optimal move for a position under certain conditions. |
| [Evaluation](#section-v-5-2-2) | Evaluates a position from an opponent's perspective.|
