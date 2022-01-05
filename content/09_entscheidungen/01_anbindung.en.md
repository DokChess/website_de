+++
title = "Frontend Connectivity"
menuTitle = "9.1 Frontend Connectivity"
weight = 1
description="How Does the Engine Communicate with the Outside World?"
url="09_decisions/01_connectivity"
+++

## 9.1 How Does the Engine Communicate with the Outside World?

### Problem Background
As a central requirement DokChess must work together with existing chess frontends.
How do we connect them?

A whole series of graphical user interfaces are available for playing against chess programs.
Moreover, there are software solutions with a larger scope for chess enthusiasts.
In addition to the game "Human vs. Machine", they offer more functionality, such as analyzing games.
Over time, new chess programs will be released -- and others will possibly disappear from the market.

Depending on how the connection with such programs is realized, DokChess can or can not communicate with specific frontend clients.
Thus, the issue affects DokChess' interoperability  with existing chess software and its adaptability to future chess software.

### Influences on the Decision

* Constraints
 * Operation of the frontend at least on Windows desktop operating systems
 * Support for freely available frontends
 * Favoring established (chess) standards ([→ 2.3 Conventions](/en/02_constraints/03_conventions/))
* Significantly Affected Quality Attributes ([→ 1.2 Quality Goals](/en/01_introduction/02_qualitygoals/))
 * Quality Goal: Using existing frontends (Interoperability)
 * Quality Goal: Platform appealing to experiments (Changeability)
 * Adaptability (to future chess software)
* Affected Risks
 * Connecting to the Frontend fails ([→ 11.1](/en/11_risks/01_frontend/))

### Assumptions

* The investigation of just a few available frontends leads to all interesting integration options.

### Considered Alternatives

In early 2011, the following chess frontends were investigated:

* Arena Chess GUI (available for free, runs on Windows)
* Fritz for Fun (commercially provided by ChessBase GmbH, runs on Windows)
* Winboard / XBoard (Open source, runs on Windows, Mac OS X, &ast;nix)

As a result, two communication protocols have been identified as options:

* Option 1: UCI Protocol (universal chess interface), see [hier](https://www.chessprogramming.org/UCI)
* Option 2: XBoard Protocol (also known as Winboard and as Chess Engine Communication Protocol), see [hier](https://www.chessprogramming.org/Chess_Engine_Communication_Protocol)

Neither of the two protocols are formally specified, but both are publicly documented.

Both protocols are text-based, and communication between the frontend and the engine is via stdin/stdout.
In both cases the front end starts the engine in a separate process.

The following Table compares the three investigated frontends to their implemented protocols:


| &nbsp;               | Arena 3 | Fritz for fun | Winboard / XBoard |
|----------------|---------|---------------|-------------------|
| UCI            | Yes     | Yes           | \-                 |
| XBoard-Protocol| Yes     | \-             | Yes               |
*Table: Protocols and Frontends*

### Decision
Under the given constraints, the quality goals can generally be achieved with both options.
Depending on which protocol is implemented, different front ends are supported.

The decision in favor of the XBoard protocol was made in early 2011.
The structure of DokChess allows us to add alternative communication protocols (UCI or other) without having to change the engine itself for this, see dependencies in the building block view ([→ 5.1](/en/05_buildingblockview/01_level1/)).

The preferred front end for Windows is Arena.
It is freely available and tops the functionality of WinBoard.
It has good debugging facilities.
For example, it can present the communication between the frontend and the engine live in a window.
Arena supports both protocols.

By opting for the XBoard protocol, other operating systems (in addition to Windows, especially Mac OS X and Linux) are also supported with freely available frontends (see the preceding table).
As such, a larger circle of interested developers may use the engine, which was finally essential.
