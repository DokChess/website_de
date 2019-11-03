+++
title = "Text UI"
pre = "5.2 "
weight = 12
url="05_buildingblockview/02_textui"
+++

## 5.2 Subsystem Text UI (Blackbox)

### Intent/Responsibility
This subsystem implements the communication with a client (for example, a graphical user interface) using the text-based XBoard protocol ([→ Decision V.9.1](/09_entscheidungen/01_anbindung/)).
It reads commands from standard input, checks them against the rules of the game and converts them for the _Engine_. Responses from the Engine (especially the moves) will be accepted by the subsystem as events, formatted according to the protocol and returned via standard output.
Thus the subsystem is driving the whole game.

### Interfaces

The subsystem provides its functionality via the Java
class _org.dokchess.textui.xboard.XBoard_.

![Classes XBoard and Main](/images/en/05_Subsystem_TextUI.png "Classes XBoard and Main")
*Fig.: Classes XBoard und Main*

----

|  Method | Short description |
|-------------------------------|--------------------------------|
| setInput   | Set the protocol input with a dependency injection (→ Concept V.8.1). Typically, the standard input (stdin), automated tests use a different source. |
| setOutput | Set the protocol output. Typically, the standard output (stdout), automated tests may use a different target. |
| setChessRules | Sets an implementation of the game rules, [→ Subsystem Rules (Black Box)](/en/05_buildingblockview/03_rules/) |
| setEngine | Sets an implementation of the engine, [→ Subsystem Engine (Black Box)](/en/05_buildingblockview/04_engine/) |
| play | Starts the actual communication (input / processing / output) in a infinite loop until the quit command. |
*Table: Methods of class XBoard*


### Files
The implementation is located below the packages   
_org.dokchess.textui..._

### Open Issues
The implementation of the XBoard protocol is incomplete.
Nevertheless it is sufficient for the requirements of DokChess.
But in particular, the following features are not supported:

* Time control
* Permanent brain (thinking while the opponent thinks)
* Draw-offers and giving up of the opponent
* Chess variants (alternative rules, such as Chess960)
