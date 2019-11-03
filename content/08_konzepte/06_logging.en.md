+++
title = "Logging"
menuTitle = "8.6 Logging"
weight = 6
url="08_concepts/06_logging"
+++

## 8.6 Logging and Tracing

For improvements and extensions the analysis capabilities provided by DokChess are of note, particularly in case of on error.

The DokChess functionality itself can be checked easily with unit tests. This is particularly true for the correct implementation of the game rules and for the game play of the engine ([→ 8.7 Testability](/en/08_concepts/07_testability/)).
It holds true for your own extensions in this area as well.

Therefore there is no fine-grained logging output within DokChess. Solutions like [SLF4J](https://www.slf4j.org) are not present.
In this way we avoid a dependency to an external library and the source code is not polluted by this aspect at all.

For the communication between the client and DokChess via the XBoard protocol -- in addition to interactive operation via a shell ([→ 8.3 User Interface](/en/08_concepts/03_userinterface/)) -- the client may monitor the conversation.
Common chess frontends permit this by writing log files and/or a simultaneous display of a log window during the game. The image below shows this functionality within Arena.


![Log and debug window for XBoard Protocol in Arena](/images/en/08_xx_ArenaEngineDebug.png)
*Fig.: Log and debug window for XBoard Protocol in Arena*

If the engine blocks and it is unclear what went on on the XBoard protocol, such tools are simply invaluable.
Due to the availability of this feature a communication protocol tracing was not implemented within DokChess at all.
