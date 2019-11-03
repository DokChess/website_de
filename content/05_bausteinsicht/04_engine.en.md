+++
title = "Engine"
pre = "5.4 "
weight = 14
url="05_buildingblockview/04_engine"
+++

## 5.4 Engine (Blackbox)

### Intent/Responsibility
This subsystem contains the determination of a next move starting from a game position.
The position is given from outside.
The engine itself is stateful and always plays one game at the same time.
The default implementation needs an implementation of the game rules to work.
An opening library, however, is optional.

### Interfaces
The _Engine_ subsystem provides its functionality via the Java interface  
_org.dokchess.engine.Engine_.

Default implementation is the class  
_org.dokchess.engine.DefaultEngine_.

![Interface Engine and class DefaultEngine](/images/en/05_Subsystem_Engine.png "Interface Engine and class DefaultEngine")

*Fig.: Interface Engine and class DefaultEngine*

----

|  Method | Short description |
|-------------------------------|--------------------------------|
| setupPieces | Sets the state of the engine to the specified position. If currently a move calculation is running, this will be cancelled. |
| determineYourMove | Starts the determination of a move for the current game situation. Returns move candidates asynchronously via an Observable  ([→ 6.1 Runtime View](/en/06_runtimeview/01_move_determination/) "Move Determination Walkthrough"). The engine does not perform the moves. |
| performMove | Performs the move given, which changes the state of the engine. If currently a move calculation is running, this will be canceled. |
| close | Closes the engine. The method makes it possible to free resources. No move calculations are allowed afterwards. |
*Table: Methods of the Engine interface*

----

|  Method | Short description |
|-------------------------------|--------------------------------|
| DefaultEngine | Constructors, set an implementation of the chess rules, [→ Subsystem Rules (Black Box)](/en/05_buildingblockview/03_rules/) and an (optional) opening book, whose moves will be preferred to own considerations, [→  Subsystem Opening (Black Box)](/en/05_buildingblockview/05_opening/). |
*Table: Methods of the DefaultEngine class (in addition to the Engine interface)*

----

[→ Concept 8.2 Chess Domain Model](/en/08_concepts/02_domainmodel/) ("Chess domain model") describes the types used in the interface as call and return parameters (_Move_, _Position_). Refer to the source code documentation (javadoc) for more information.

You find details of the _Engine_ subsystem implementation in the white box view in section [5.6](/en/05_buildingblockview/06_level_2_engine/) of this overview.

### Files
The implementation of the _Engine_ subsystem and corresponding unit tests are located below the packages   
_org.dokchess.engine..._
