# Microservice Patterns

By Chris Richardson - published in November 2017

> The monolithic architecture works well for small, simple applications. However, successful applications have a habit of growing. Eventually the development team ends up in what is known as monolithic hell. All aspects of software development and deployment become painfully slow. The solution is to adopt the microservice architecture, which structures an application as a services, organized around business capabilities. This architecture accelerates software development and enables continuous delivery and deployment of complex software applications.
  
> _Microservice Patterns_ teaches enterprise developers and architects how to build applications with the microservice architecture, which you'll discover is not a silver bullet and has both benefits and drawbacks. Along the way, you'll learn a pattern language that will enable you to solve the issues that arise when using this architectural style. This book also teaches you how to refactor a monolithic application to a microservice architecture.

1. Escaping Monolithic Hell
2. Decomposition Strategies
3. Inter-Process Communication in a Microservice Architecture
4. Managing Transactions with Sagas
5. Designing Business Logic in a Microservice Architecture
6. Developing Business Logic with Event Sourcing
7. Implementing Queries in a Microservice Architecture
8. External API Patterns
9. Testing Microservices
10. Microservices in Production
11. Refactoring to Microservices


### 1. Escaping Monolithic Hell

> - What is monolithic hell and how to escape it by adopting microservices
> - Benefits and drawbacks of microservices
> - The goal of the microservices pattern language
> - Success = microservices + small, agile teams

TODO

### 2. Decomposition Strategies

> - What is software architecture and why it is important
> - How to decompose an application into services
> - How to use the bounded context concept from Domain-Driven Design to untangle data and make decomposition easier

The essence of the microservice architecture is functional decomposition, hence its first and most important aspect is the definition of the services.

##### 2.1 Purpose of Architecture

> The Software architecture of a computing system is the set of structures needed to reason about the system, which comprises software elements, relations among them, and properties of both.
> -- _Documenting Software Architectures Bass_ et al

An application's architecture can be viewed from multiple perspectives, typically via the [4+1 View Model](https://en.wikipedia.org/wiki/4%2B1_architectural_view_model).

![4 + 1 View Model](images/2.1.four.plus.one.view.model.png?raw=true)

The four views are
* Logical view - classes, state diagrams, etc
* Process view - the processes and how they communicate
* Physical view - the physical (virtual machines) and network connections
* Development view - components

Then the scenarios "animate" the views by describing how the various components within each view collaborate.

An application has two categories of requirements : 
* Functional Requirements : what the application must do
* Quality Attributes :
  * Runtime Qualities : scalability and reliability
  * Development Time Qualities : maintainability, testability, extensibility, deployability

The microservice architecture is an architectural style that structures an application as a set of **loosely coupled services** primarily organized around **business concepts** (rather than technical concepts).<br>   
The requirement for services to be loosely coupled and to collaborate via APIs prohibits services from communicating via a database. A service's persistent data is equivalent to the fields of a class and must be kept private.


