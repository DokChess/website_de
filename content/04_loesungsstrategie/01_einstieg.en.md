+++
title = "Introduction"
pre = "4.1 "
weight = 10
url = "04_solutionstrategy/01_introduction"
+++

## 4.1 Introduction to the Strategy

The following table contrasts the quality goals of DokChess (→ [Section 1.2](/en/01_introduction/02_qualitygoals/)) with matching architecture approaches and thus provides easy access to the solution.


|Quality Goal     |Matching approaches in the solution|
|---------------|--------------------------------------------|
| Accessible example (Analysability) | <ul><li>architectural overview structured by arc42</li><li>explicit, object-oriented domain model</li><li>detailed documentation of public interfaces with Javadoc</li></ul>|
| Platform appealing to experiments (Changeability) | <ul><li>widely spread programming language Java →&nbsp;**(a)**</li><li>Interfaces for core abstractions (for instance: position evaluation, game rules)</li><li>immutable objects (position, move, ... ) make implementation of many algorithms easier</li><li>"plugging" of elements with dependency injection leads to interchangeability →&nbsp;**(b)**</li><li>High test coverage as a safety net</li></ul>|
| Using existing frontends (Interoperability) | <ul><li>Use of the common communication protocol XBoard, →&nbsp;**\(c\)**</li><li>Use of portable Java →&nbsp;**(a)**</li></ul>|
| Acceptable playing strength (Attractiveness) | <ul><li>Integration of chess opening book libraries →&nbsp;**(d)**</li><li>implementation of minimax algorithm and a proper position evaluation →&nbsp;**(e)**</li><li>Integration tests with chess problems for tactics and mate positions</li></ul>|
| Quick response to opponent's moves (Efficiency) | <ul><li>Reactive extensions for concurrent calculation with newly found better moves as events → **(f)** </li><li>Optimization of minimax by alpha-beta pruning →&nbsp;**(e)** </li><li>Efficient domain model implementation</li><li>Integration tests with time limits</li></ul>|


Small letters in brackets, e.g. →&nbsp;**(x)**, link individual approaches from the right hand of the table to the following architectural overview diagram.
The remaining section 4 introduces significant architectural aspects and refers to further information.

![DokChess Architectural Overview Diagram](/images/en/04_01_DokChessOverview.png "DokChess Architectural Overview Diagram")
*Fig.: DokChess Architectural Overview Diagram*
