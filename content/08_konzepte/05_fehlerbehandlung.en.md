+++
title = "Error Handling"
menuTitle = "8.5 Error Handling"
weight = 5
url="08_concepts/05_errorhandling"
+++

## 8.5 Exception and Error Handling

DokChess has no own user interface. Therefore it must indicate problems to the outside world.

All DokChess subsystem methods throw Runtime Exceptions.
In addition in case of the _Engine_ subsystem error messages (_onError_) may occur during an asynchronous search.
Your own extensions (for example a custom search) must be implemented accordingly.
Checked exceptions (e.g. _java.io.IOException_) need to be wrapped in Runtime Exceptions.

The javadoc of methods and constructors in question shows the rare cases where exceptions are expected in DokChess.
Trouble reading an opening book file, or when trying move calculation within the engine at an invalid position (if identified).
All other exceptions would be programming errors (please report them under https://github.com/DokChess/).

The Text UI subsystem catches all exceptions and communicates them via the XBoard protocol outwards (command "tellusererror").
A graphical front-end usually visualizes them in an error dialog or alert box.
The image below depicts that for the chess frontend Arena.

![An error dialog in Arena](/images/en/08_xx_ArenaErrorMessage.png "An error dialog in Arena")
*Fig.: An error dialog in Arena*

DokChess continues to work "normally".
The client decides whether proceeding in this specific situation makes sense.
For example, it could continue to play without an opening book.
