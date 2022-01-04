+++
title = "Windows Infrastructure"
menuTitle = "7.1 Windows Infrastructure"
weight = 11
url="07_deploymentview/01_windows_infrastructure"
+++

## 7.1 Windows Infrastructure
The following deployment diagram shows the use of DokChess on Windows without an opening book.
Arena is used as an example frontend ([→ Decison 9.1](/en/09_decisions/01_connectivity/) "How does the engine communicate with the outside world?").

![Deploying DokChess on a Windows PC](/images/en/07_01_Deployment_Windows.png "Deploying DokChess on a Windows PC")
*Fig.: Deploying DokChess on a Windows PC*

Software Requirements on a PC:

* Java Runtime Environment SE 11 (or higher)
* The JVM (javaw.exe) is in the _PATH_, otherwise adapt _dokchess.bat_
* [Arena](http://www.playwitharena.de)

DokChess.jar contains the compiled Java source code of all the modules and all the necessary dependencies ("Uber-jar").
The script file _dokchess.bat_ starts the Java Virtual Machine with DokChess. Both are available on the computer in a common directory, because _dokchess.bat_ relatively addresses the jar file.

Within Arena, the script file is declared in the following menu "Engine | Install a new Engine ...".
You will see a file selection, the file type can be limited to _* .bat_ files.
Then, set the engine type to "Winboard".
In other chess frontends, declaring an engine is very similar
See corresponding documentation for details.

### Open Issues
Some frontends under Windows only allow the integration of a \*.exe file as an engine.
In this case DokChess would have to be wrapped appropriately.
