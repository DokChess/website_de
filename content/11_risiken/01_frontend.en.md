---
title: "Frontend Connection"
pre: "11.1 "
weight: 1
url: "11_risks/01_frontend"
---

## 11.1 Risk: Connecting to the Frontend fails
There is no knowledge about connecting an engine to an existing chess frontend.
Available open source engines are programmed in C and are delivered as executable programs (_*.exe_).
Since DokChess is developed in Java, they are of limited use as examples.
Nothing is known in the project about chess communication protocols.

If it is not possible to make a working connection, the solution can not be used with existing frontends.
This not only lacks an important feature ([→ 1.1 Requirements Overview](/en/01_introduction/01_requirements/)), but also makes the solution as a whole, especially as a case study, untrustworthy.

### Contingency Planning
A simple textual user interface could be implemented in order to interact with the engine. The implementation of a DokChess specific graphical front end would be costly ([→ 11.2 "Effort of Implementation"](/en/11_risks/02_effort/)).

### Risk Mitigation
Through an early proof of concept, certainty is achieved as soon as possible here.
