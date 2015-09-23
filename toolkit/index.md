---
layout: page
title: Development Toolkit
date: 20 September 2015
comments: false
categories: [tools]
sharing: true
---

*Just sketching in the dev environment for now...*

## Development Environment

Minimum environment:

* Visual Studio 2015 Community Edition
* SQL Server LocalDB

Suggested:

* Visual Studio Code for any HTML, CSS, JS work.

## Testing

* Unit Test: xUnit.Net. Suggest installing the Visual Studio runner.
* Mocking: Moq
* Desired code-coverage: 80%
  * VS Community does not have code coverage. Need to setup OpenCover.

## Front-End

* Angular.js
* HTML 5
* CSS 3
* Bootstrap (Angular version)

## Back-End

* API routing: WebApi
  * I strongly considered Node.js, PHP, and Python - but the reality
    is that finding hosting for Node.js and Python is expensive,
	and I hate PHP. Also, in recruiting for an open source team,
	I needed to target to the framework that my friends are already
	comfortable in.
* Hypermedia specification: Collection+JSON or HAL or Siren (undecided)
* DB: SQL Server 2014
* Auth: ASP.NET Identity Framework
* ORM: EntityFramework (tentative)
  * Considering NServiceKit.OrmLite or Dapper as alternatives.
  * Why use EF at all? Code migrations. And because it is a useful
    skill to have, even if there are much higher performing 
	frameworks
* Architecture: Onion


## Lifecycle Management

* Source Control: GitHub
* Artifacts: possibly post directly to NuGet, bower.
* Integration: AppVeyor (future)
* Deployment: AppVeyor (future)