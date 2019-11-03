+++
title = "Testability"
menuTitle = "8.7 Testability"
weight = 7
url="08_concepts/07_testability"
+++

## 8.7 Testability

Nothing is more embarrassing for an engine than an illegal move.

The functionality of the individual modules of DokChess is ensured by extensive unit tests. You find a folder _src/test_ next to _src/main_, where the Java source code of the modules is stored. It mirrors the package structure, and in the corresponding packages unit tests for the classes realized with [JUnit 4](https://junit.org/junit4/).

Standard unit testing, which examine the individual classes, are named as the class itself with suffix _Test_.
In addition, there are tests that examine the interaction of modules, and in extreme cases the whole system.
With the help of such tests, the correct playing of DokChess is checked.
More complex, long-running integration tests are below _src/integTest_. This includes playing entire games.

In many tests positions must be provided as call parameters. Here the Forsyth-Edwards Notation (FEN in short) is used. This notation allows the specification of a complete game situation as a compact string without a line break and is therefore perfect for use in automated tests.

The starting position in FEN for example is denoted:

    "rnbqkbnr/pppppppp/8/8/8/8/PPPPPPPP/RNBQKBNR w KQkq - 0 1"

Lowercase letters stand for black, uppercase for white pieces. For the piece types the English names (r for rook, p for pawn  ...) are used.

![Sample position](/images/en/08_xx_SamplePositionDiagram.png "Sample position")
*Fig.: Sample position*

The game situation in the picture above with white before the 79th move, with 30 half-moves long no piece was captured and no pawn was moved, looks like this in FEN

    "6r1/6pp/7r/1B5K/1P3k2/N7/3R4/8 w - - 30 79"

and reads "6 squares free, black rook, square free, new rank ...".

Details about the notation can be found for example at [Wikipedia](https://en.wikipedia.org/wiki/Forsyth–Edwards_Notation). The _Position_ class has a constructor that accepts a string in FEN. The _toString_ method of this class also provides FEN.

In addition to tests for correct functionality, it is also checked whether the required response times for exemplary game situations can be met.
This is done with the _@Test_ annotation and its timeout parameters. The success of these tests depends on the hardware used.
