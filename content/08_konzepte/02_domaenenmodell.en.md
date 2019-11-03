+++
title = "Domain Model"
menuTitle = "8.2 Domain Model"
weight = 2
url="08_concepts/02_domainmodel"
+++

## 8.2 Chess Domain Model

> "The game of chess is played between two opponents who move their pieces on a square board called a ‘chessboard’.""
>
> from the FIDE Laws of Chess

The different modules of DokChess exchange chess-specific data. This includes the game situation on the chessboard (position) for instance, as well as opponent's and own moves. All interfaces use the same domain objects as call and return parameters.

This section contains a brief overview of these data structures and their relationships. All the classes and enumeration types (enums) are located in the _org.dokchess.domain_ package. See the source documentation (_javadoc_) for details.

A chess piece is characterized by colour (black or white) and type (king, queen, and so on).
In the DokChess domain model, a piece does not know its location on the board.
The _Piece_ class is immutable, and so are all other domain classes.

![A piece has a colour and a type](/images/en/DomainModel_1.png "A piece has a colour and a type")
*Fig.: A piece has a colour and a type*

A chessboard consists of 8 x 8 squares, which are arranged in 8 rows called _ranks_ (1-8) and 8 columns called _files_ (a-h).
The _Square_ class describes one of these.
Since a square can be occupied by only one piece, source and target squares are sufficient to specify a move (the _Move_ class).
The only exception is the promotion of a pawn on the opponent's baseline.
Here, the player decides which piece type they want to convert the pawn to (typically, but not necessarily, a queen).
Castling moves are represented as king moves over two squares in the corresponding direction. The additional attributes for the moving piece and whether the move is a capture are useful for the analysis tasks of the engine.


![A move from square to square](/images/en/DomainModel_2.png "A move from square to square")
*Fig.: A move from square to square*

The _Position_ class describes the current situation on the board.
In particular, these are the piece locations on the board, which are internally represented as a two-dimensional array (8 x 8).
If a square is not occupied, _null_ is stored in the array.
To complete the game situation, the _Position_ class includes information about which side moves next, which castlings are still possible (if any), and whether capturing en passant is allowed.

![A position describes a game state](/images/en/DomainModel_3.png "A position describes a game state")
*Fig.: A position describes a game state*

The _Position_ class is immutable as well. Therefore, the _performMove()_ method returns a new position with the modified game situation (→ decision V.9.2 "Are position objects changeable or not?").
