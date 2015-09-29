---
layout: page
title: System Architecture
comments: false
category: programming
tags: [architecture]
sharing: true
---

## Design Principles

### Loose Coupling

One of the core principles of this project is that of loose coupling. We want 
to build sets of components that can be separated from each other easily, thus
allowing re-mixing of solutions, a high degree of code sharing, and simple
replacement of components.

### Micro Services

The micro service concept is a powerful way to achieve loose coupling. In comes
down to this: instead of putting all of your API services into one project,
you spread them out into several coherent packages, each of which is ideally
installed separately. This lowers your risk when it is time to update or replace 
components. Because FlightNode software is likely to be installed on low
budget shared servers, literally having separate service installs might be a hassle,
so we'll try to build services in such a way that they can run standalone or
integrated with other projects. 

### Careful Encapsulation

Along with these principles, we will be careful to encapsulate object and package
data in ways that foster loose coupling without dragging the project down into
too much complexity. On the API side, we'll use the Onion Architecture concept
with a focus on good Domain design. Infrastructure classes - that is, concrete
realizations of I/O interfaces - will be implemented in separate libraries. In this
way, Domain projects need not change if the persistence layer changes, for 
example from SQL Server to MySQL or even from one ORM to another.

## System Design

### Interaction

Typical interaction with secured component:

```
  O        Identity         DataCollection     Database  
 /|\       --------         --------------     ----------  
  |   -->  Authenticate  
 / \  <--  (token)  
      (token,data) -------> SubmitData  
           Validate  <----- (token)     
                            (data) -----------> Save       
```

### Component Projects

#### FlightNode.Demo

Angular.js website serving as a demonstration / reference implementation of
the FlightNode platform.

https://github.com/FlightNode/FlightNode.Demo

#### FlightNode.Identity

.NET 4.5.2 package based on ASP.NET Identity, providing authentication and authorization
using OAuth2.

https://github.com/FlightNode/FlightNode.Identity

#### FlightNode.DataCollection

.NET 4.5.2 package providing data collection and reporting capabilities. May need to
include user management here.

https://github.com/FlightNode/FlightNode.DataCollection

#### FlightNode.Common

.NET 4.5.2 library for cross-cutting concerns used in the other projects.

https://github.com/FlightNode/FlightNode.Common

#### flightnode.github.io

Source files for this website.