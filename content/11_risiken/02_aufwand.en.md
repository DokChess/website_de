+++
title = "Effort"
pre = "11.2 "
weight = 2
url="11_risks/02_effort"
+++

## 11.2 Risk: Implementation effort too high

There is no experience with chess programming.
Simultaneously, the rules that are to be implemented completely ([→ 1.1 Requirements Overview](/en/01_introduction/01_requirements/)) are extensive and complicated.
The different pieces move differently, and there are special rules such as stalemate and promotion.
In the case of castling and en passant, the move history, and not only the current situation on the board, is relevant.

The programming of the algorithms is also non-trivial. For the connection of opening libraries and endgame databases, extensive research is required.

The implementation of DokChess runs as a hobby alongside, within the spare time.
It is unclear whether this is sufficient to present ambitious results within schedule ([→ 2.2 Organizational Constraints](/en/02_constraints/02_organizational/)).


### Contingency Planning

If there is no runnable version for the conference sessions in March and September 2011, a live demonstration could be omitted.
The free evening talk at oose in March could even be canceled completely (which could negatively affect the reputation).


### Risk Mitigation

In order to reduce effort, the following rules are not implemented at first:

* 50 moves rule  
* threefold repetition

Their absence has little consequence with respect to the playing strength, and consequence no consequence with respect to the correctness of the engine.

Connecting opening libraries and endgame databases has low priority and and takes a back seat at first.
