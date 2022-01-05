+++
title = "Position Objects"
menuTitle = "9.2 Position Objects"
weight = 2
description="Are Position Objects Changeable or Not?"
url="09_decisions/02_positionobjects"
+++

## 9.2 Are Position Objects Changeable or Not?

### Problem Background

For various DokChess modules, game situations on the chess board (so-called positions) must be provided and exchanged between them.
Do we make the associated data structure changeable or unchangeable (immutable)?

During a game, the position changes when the opposing players move their pieces.
In addition, the engine performs possible moves in its analysis, tries to counter the moves of the opponent, evaluates the outcoming positions, and then discards moves.
The result is a tree that contains many thousands of different positions, depending on the search depth.

Depending on whether the position is immutable as a data structure or not, algorithms are easier or more difficult to implement, and its execution is efficient in a different way.

All modules depend on the position interface. A subsequent change would affect all of DokChess.

### Influences on the Decision

* Constraints ([→ 2.1 Technical Constraints](/en/02_constraints/01_technical/))
 * Implementation in Java
 * Moderate hardware equipment
* Significantly Affected Quality Attributes ([→ 1.2 Quality Goals](/en/01_introduction/02_qualitygoals/))
 * Quality Goal: Platform appealing to experiments (Changeability)
 * Quality Goal: Acceptable playing strength (Attractiveness)
 * Quality Goal: Quick response to opponent's moves (Effizienz)
* Affected Risks
 * Implementation effort too high ([→ 11.2](/en/11_risks/02_effort))
 * Achieving the playing strength fails ([→ 11.3](/en/11_risks/03_playingstrength))

### Assumptions

* It is possible to implement a data structure with a fine-grained object model (that is, classes such as Piece and Move) that is efficient enough to provide the required playing strength within an adequate response time.
* In the future, concurrent algorithms should be implemented with the data structure as well.

### Considered Alternatives

The starting point is domain-driven classes for square, piece and move ([→ 8.2 Chess Domain Model](/en/08_concepts/02_domainmodel/)).
These classes are realized immutable as value objects (the e4 field always remains e4 after it's construction).

For the position, two alternatives are considered:

* **Option (1)**: The position is changeable. Individual methods of the interface, for example, performing moves or taking them back, change the object state.

<pre>// Pseudocode
Position p = new Position(); // starting position, white side to move
p.performMove(e2e4);         // king's pawn advances two squares, black to move
p.takeBackLastMove()         // starting position again
...
</pre>

* **Option (2)**: The position is unchangeable ("immutable"). That means a method for performing a move provides the new position (it copies the old one, then the move happens) as another immutable object as the result.

<pre>Position p = new Position();
newPosition = p.performMove(e2e4); // p keeps unchanged
...
</pre>

The following table summarizes the strengths and weaknesses of the two options, they are explained below.

| &nbsp;              | (1) changeable    | (2) unchangeable    |
|----------------|-----------------|-------------------|
| Implementation effort | **(-)** higher     | **(+)** lower           |
| Efficiency (memory consumption) | **(+)** more economical | **(-)** higher demand |
| Efficiency (time behaviour) | **(o)** neutral     | **(-)** worse           |
| Suitability for concurrent algorithms | **(-)** bad     | **(+)** good           |
*Table: strengths and weaknesses of the two options*


#### Option (1): The Position is Changeable

(+) Positive Arguments

The position with its extensive state is not copied in each move.
This saves memory and CPU time, and it treats the garbage collector with care.
For analysis algorithms, however, it is necessary to implement functionality that takes back the effect of moves ("undo").
This Undo also takes time, hence the neutral rating **(o)** for the time behavior.

(-) Negative Arguments

The implementation of an Undo-functionality is complex.
Not only does it have to set up captured pieces back on the board, the castling rule and en passant require special treatment as well.
The Gamma+94 Command pattern suggests itself as an option.
The use of that pattern within algorithms is also more complex because the latter must explicitly call methods to take back the moves.

Finally, changeable state has drawbacks related to concurrency.

#### Option (2): The Position is Unchangeable

(+) Positive Arguments

When you perform a move, the position is copied.
It does not change the original.
This eliminates the implementation of move reversal (Undo).
Clients can simply store the old position as a value.
This saves effort in the implementation compared to option (1).

Immutable objects offer significant advantages in concurrent algorithms.

(-) Negative Arguments

Copying the state for each new position takes time.
When analyzing situations, it covers many positions, which can take a lot of time.

Beyond that, copying the state for each new position costs memory.
The implementation of search algorithms with backtracking at least prevents complete game trees from ending up on the heap.
Nevertheless, more memory is required, and the garbage collector has more work to do.

Both points have a negative effect on efficiency.

### Decision

The decision for the unchangeable position (option 2) was made in early 2011 due to the advantages in terms of ease of implementation and the prospect of exploiting concurrency.
All the disadvantages of option 2 are related to efficiency.

Due to the risk of failing to achieve the objectives with respect to the playing strength in an acceptable computing time (attractiveness, efficiency), prototypes of both versions have been implemented and compared in a mate search (Checkmate in three moves) with the minimax algorithm.
With option 2, the search took 30% longer, assuming you implement copying efficiently.
But this option met the constraints still well.

Further optimization options could reduce the efficiency disadvantage compared with option 1, if necessary.
But they have not been implemented in the first run in order to keep the implementation simple.

These options included the use of multiple processors/cores with concurrent algorithms.
In the meantime (with DokChess 2.0), this was illustrated with a parallel minimax example.
