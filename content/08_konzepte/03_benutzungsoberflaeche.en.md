+++
title = "User Interface"
menuTitle = "8.3 User Interface"
weight = 3
url="08_concepts/03_userinterface"
+++

## 8.3	User Interface

DokChess itself has no graphical user interface.
It interacts via the XBoard protocol with the outside world ([→ Decision 9.1](/en/09_decisions/01_connectivity/) "How does the engine communicate with the outside world?").

The XBoard protocol is text-based.
If you have mastered the main commands (see Figure ...) starting DokChess in a command line (Unix shell, Windows command prompt, ...) enables you to interact with the engine.
The table below shows a sample dialog, all commands are terminated with a new line). By default the engine plays black. You can change this with the "white" command of XBoard.

|Client → DokChess|DokChess → Client|Comments|
|-----------------|-----------------|--------|
| _xboard_          | &nbsp;                 | client wants to use the XBoard-Protocol (required since engines partly understand other, sometimes even multiple protocols) |
| &nbsp;            | (new&nbsp;line)                |   |
| _protover&nbsp;2_          | &nbsp;                 | protocol version 2 |
| &nbsp;            | _feature&nbsp;done=1_ | line by line notification of additional features of the engine (here: none) |
| _e2e4_          | &nbsp;                 | white plays pawn e2-e42 |
| &nbsp;            | _move&nbsp;b8c6_ | black (DokChess) plays knight b8-c6 |
| _quit_          | &nbsp;                 | client ends the game (DokChess terminates) |

*Table: Example communication bewtween a client and DokChess (XBoard)*

[Mann+2009](https://www.gnu.org/software/xboard/engine-intf.html) describes the protocol itself in detail. In DokChess the Text UI subsystem is responsible for the protocol implementation  ([→ Building Block View 5.2](/en/05_buildingblockview/02_textui/)).

A more typical use of DokChess is a graphical chess frontend like Arena (see image below). It accepts the moves of the opponent in a comfortable interface, passes them to DokChess in the form of XBoard commands like in the table above (column "Client → DokChess") and translates the answers (column "DokChess → Client") graphically.

![DokChess combined with the Arena chess frontend under Windows](/images/en/08_xx_ArenaDokChess.png "DokChess combined with the Arena chess frontend under Windows")
*Fig.: DokChess combined with the Arena chess frontend under Windows*
