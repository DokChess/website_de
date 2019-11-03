+++
title = "Opening"
pre = "5.5 "
weight = 15
url="05_buildingblockview/05_opening"
+++

## 5.5 Subsystem Opening (Blackbox)

### Intent/Responsibility
This subsystem provides opening libraries and implements the Polyglot opening book format.
This format is currently the only one available, which is not proprietary.
Corresponding book files and associated tools are freely available on the Internet.


### Interfaces
The _Opening_ subsystem provides its functionality via the Java interface  
_org.dokchess.opening.OpeningLibrary_.

The class _org.dokchess.opening.polyglot.PolyglotOpeningBook_ provides one possible implementation.

![Interface OpeningLibrary and class PolyglottOpeningBook](/images/en/05_Subsystem_Opening.png "Interface OpeningLibrary and class PolyglottOpeningBook")

*Fig.: Schnittstelle Eroeffnungsbibliothek, Implementierung PolyglotOpeningBook*

----

|  Method | Short description |
|-------------------------------|--------------------------------|
| lookUpMove | Returns a standard move for the specified position from the library, or null. |
*Table: Methods of the interface OpeningLibrary*


#### PolyglotOpeningBook
The _PolyglotOpeningBook_ class is an adapter for the Polyglot opening book file format.
Implementation of _OpeningLibrary_ that reads a binary file in the appropriate format and returns a move to the specified position, if the library contains any.


|  Method | Short description |
|-------------------------------|--------------------------------|
| PolyglotOpeningBook | Constructor, expects the input file. |
| setSelectionMode | Sets the mode to select a move, if there is more than one candidate in the library for the given position. |
*Table: Methods of the class PolyglotOpeningBook (in addition to interface OpeningLibrary):*

----

[→ Concept 8.2 Chess Domain Model](/en/08_concepts/02_domainmodel/) describes the types used in the interface as call and return parameters (_Move_, _Position_).

### Files
The implementation, unit tests and test data for the Polyglot file format are located below the packages   
_org.dokchess.opening..._

### Open Issues
* The implemented options for a move selection from the Polyglot opening book in case of several candidates are limited (the first, the most often played, by chance).
* The implementation can not handle multiple library files at the same time. It can therefore not mix them to combine the knowledge.
