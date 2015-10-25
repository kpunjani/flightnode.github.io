---
layout: page
title: Development Toolkit
comments: false
category: programming
tags: [toolkit]
sharing: true
---

## Development Environment

Minimum environment:

* Visual Studio 2015 Community Edition
* SQL Server LocalDB

Suggested:

* [Visual Studio Code](https://code.visualstudio.com/Docs) for any HTML, CSS, JS work.
  * The [TypeScript Definition manager](http://definitelytyped.org/tsd/) is used for installing
    IntelliSense definition files. Install `tsd` globally using `npm -g install tsd`.
  * As with bower, npm, etc., you need to run install anytime the tsd.json file changes. This 
    will download type definitions and install them into the *typings* directory. At a command
    prompt, just run `tsd install`.    
  * These typings give you lovely IntelliSense within VSCode, but they don't help with JSHint.
    To eliminate JSHint warnings on legitimate globals, add the library name to the .jshintrc
    file.

## Workspace Setup

* Fork your repositories off of the main repositories of FlightNode.
* Install Git 2.x using Chocolatey. 
* Locally, create a directory called `c:\Workspaces\FlightNode` (or any name of your choice).
* Run Git-Bash (you'll may want to pin it to the taskbar or dock for easy access)
* Create your local copies of your GitHub repositories 

```bash
mkdir FlightNode
cd FlightNode 
git clone https://github.com/*<username>*/FlightNode.Identity
git clone https://github.com/*<username>*/FlightNode.Common
git clone https://github.com/*<username>*/flightnode.Demo
git clone https://github.com/*<username>*/flightnode.DataCollection
```

New to Git? [Here are some tips and tutorials](/archive/2015/10/24/git-tutorials-etc) 

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