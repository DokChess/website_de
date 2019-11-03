+++
title = "Level 1"
pre = "5.1 "
weight = 11
url="05_buildingblockview/01_level1"

+++

## 5.1	Building Block View, Level 1

DokChess breaks down in four subsystems as presented below. The dashed arrows represent logical dependencies between the subsystems ("x -> y" for "x depends on y").
The squared boxes on the membrane of the system are interaction points ("ports") with the outside world ([→ 3.2 Deployment Context](/en/03_context/02_deployment/)).

![DokChess, building block view, level 1](/images/en/05_BuildingBlocks_Level_1.png "DokChess, building block view, level 1")
*Fig.: DokChess, building block view, level 1*

----

|  Subsystem | Short description |
|-----------|------------------|
| [Text UI](/en/05_buildingblockview/02_textui/)   | Realizes communication with a client using the XBoard protocol. |
| [Rules](/en/05_buildingblockview/03_rules/) | Provides the rules of chess and for instance can determine all valid moves for a position. |
| [Engine](/en/05_buildingblockview/04_engine/) | Contains the determination of a next move starting from a game situation. |
| [Opening](/en/05_buildingblockview/05_opening/) | Provides standard moves of the chess opening literature for a game situation. |
*Table: Subsystems overview of DokChess*

Section [→ 6.1 "Move Determination Walkthrough"](/en/06_runtimeview/01_move_determination/) contains an example of the interaction between the subsystems at runtime.
