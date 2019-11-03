+++
title = "Dependencies"
menuTitle = "8.1 Dependencies"
weight = 1
url="08_concepts/01_dependencies"
+++

## 8.1 Dependencies Between Modules

DokChess invites developers to experiment and to extend the engine ([→ 1.1 Requirements Overview](/en/01_introduction/01_requirements/)).
In order to do so, the modules are loosely coupled.
DokChess modules are implementations of Java interfaces.
Java classes that require parts signal this with appropriate methods _set«Module»(«Interface» ...)_.
They don't take care of resolving a dependency, for instance, by using a factory.
Instead, the client resolves the dependencies by creating suitable implementations with _new_ and putting them together with setter methods (also known as [Dependency Injection](https://martinfowler.com/articles/injection.html), short DI).

Interfaces and DI enable alternative implementations within DokChess. Adding functionality with the help of the decorator pattern (Gamma+94) is possible as well.
Furthermore, aspect-oriented programming (AOP) solutions, which rely on Java dynamic proxies, are applicable interfaces.
Plus, this handling of dependencies positively affects testability ([→ 8.7 Testability](/en/08_concepts/07_testability/)).

DokChess abstains from the use of a concrete DI framework. The modules are hard-wired in the code, however only in unit tests and glue code (for example, the _main_ class). No annotation driven configuration is present in the code.

This gives adventurous developers free choice regarding a specific DI implementation.
Since the Java modules are pure POJOs (Plain Old Java objects),  nothing prevents configuration with the [Spring Framework](https://projects.spring.io/spring-framework/) for example or CDI (Contexts and Dependency Injection for the Java EE Platform).
