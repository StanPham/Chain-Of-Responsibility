# Chain Of Responsiblity Pattern

## Definiton

###  Chain of Responsibility is a behavioral design pattern that lets you pass requests along a chain of handlers. Upon receiving a request, each handler decides either to process the request or to pass it to the next handler in the chain.

![solution1-en](https://user-images.githubusercontent.com/128852758/230756692-80f62763-a46f-4680-92ae-77882a615287.png)

![chain-of-responsibility-comic-1-en](https://user-images.githubusercontent.com/128852758/230756954-97780078-a9c5-4ed1-8fb7-3fa61875e97f.png)


## Similarities to the Decorator Pattern

### Decorator UML
![DecoratorPattern](https://user-images.githubusercontent.com/128852758/230757547-b88f5392-d416-4f01-99cc-bf86b400ecdf.png)
* Everything inherits from Component
* Decorators contain an instance of a Component

<br />

### Beverage Example
![Decorator Example](https://user-images.githubusercontent.com/128852758/230758079-3a1adfa5-9b3f-4cfa-9dc6-f2473550ac69.png)
* Cost is being compounded by each Component

<br />

### Chain of Responsibility UML
![UMLDiagram](https://user-images.githubusercontent.com/128852758/230758132-45d7331e-1b56-4992-9132-0dfed070b1d5.png)

<br />

### Movie UML
![MovieUML](https://user-images.githubusercontent.com/128852758/230761508-dcd4d8ab-b570-47b7-bdcb-80e1e281ff1d.png)


<br />
<br />

# Strengths

### Single Responsibility Principle
* A request is separated into multiple Handlers
* Each Handler is responsible for dealing requests that it can process.

### Loosely Coupled Principle
* The Client only interacts with the Handler interface.
* The Client never interacted with the Movie get functions directly.
* This reduces the dependencies between components which makes it easier to maintain.

### Open-Closed Principle
* We can add Handlers to the system without changing the ones that exist already.
* Adding and removing Handlers doesn't affect the rest of the system.

<br />

# Weaknesses

### Performance
* Each request has to go through multiple Handlers which adds performance overheads.
* Longer chains have more performance loss for this reason.

### Debugging
* It can be hard to tell where in the chain a problem is occuring.
* You have to ensure that a request will eventually get resolved.

<br />

# Real World Examples

## Error Logging
![chainofresponsibilityuml](https://user-images.githubusercontent.com/128852758/230761135-f41e981f-b714-4c9b-9c4a-aaffc55f14c7.jpg)

Each Logger only activates if the error level is severe enough.

## GUI Event Handling
![solution2-en](https://user-images.githubusercontent.com/128852758/230761630-6759f44a-ca56-457a-a9b2-80cb86de3edd.png)

The GUI framework creates a chain of event handlers that are responsible for processing user input events.
