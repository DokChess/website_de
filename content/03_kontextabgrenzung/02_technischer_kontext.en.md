+++
title = "Deployment Context"
menuTitle = "3.2 Deployment Context"
weight = 2
url = "03_context/02_deployment"
+++

## 3.2 Deployment Context

![Technical communication of DokChess with third parties](/images/en/03_02_DeploymentContext.png "Technical communication of DokChess with third parties")
##### Fig.: Technical communication of DokChess with third parties

-----

#### XBoard client (external system)
A human player is connected to DokChess with a graphical front-end. The development of such is not part of DokChess. Each graphical frontend can be used instead, if it supports the so-called XBoard protocol. These include Xboard (or Winboard on Windows), Arena and Aquarium.

#### Polyglot Opening Book (external system)
Polyglot Opening Book is a binary file format for opening libraries. DokChess allows the optional connection of such books. Only read access is used.

-----

#### On endgames
The implementation of a connection to endgame databases (such as [Nalimov Endgame tablebases](https://en.wikipedia.org/wiki/Endgame_tablebase)) has been dropped due to the effort of implementation (|→ Risk 11.2](/en/11_risks/02_effort/) Effort of implementation). The design, however, is open to appropriate extensions.
