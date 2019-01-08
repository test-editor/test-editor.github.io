---
layout: page
title: Developer Quick Start
permalink: /te_markdown/developer-quick-start/
---

Estimated reading time: 5 minutes

The **Test-Editor* is basically composed of three projects (all open source, all hosted on github.com)
1. [Test-Editor-Web](https://github.com/test-editor/test-editor-web), the UI project
2. [Test-Editor-Backend](https://github.com/test-editor/test-editor-backend), the dropwizard java backends providing `REST` services for the UI
3. [Test-Editor-Xtext-Gradle](https://github.com/test-editor/test-editor-xtext-gradle), the xtext language running under the hood

The development environment for each of the projects can be installed with just a couple of shell commands.
E.g. (for test-editor-xtext-gradle):
```
git clone https://github.com/test-editor/test-editor-xtext-gradle.git
curl https://nixos.org/nix/install | sh   # get nix package manager (if you happen to not have it installed)
cd test-editor-xtext-gradle
nix-shell                                 # setup build environment (takes a bit on first invocation)
./gradlew build
```

## Test-Editor-Web (UI project)
 
To locally setup the development environment, follow the setup section within the readme of the project [here](https://github.com/test-editor/test-editor-web#setup-development). 
Don't worry, it is setup in no time with just a couple of shell commands.
Prerequisite is an installation of linux with curl and git, all other dependencies are pulled by the respective shell.nix (using the nix package manager).

You can edit the project files (mostly typescript) with an editor of your choice (e.g. Visual Studio Code, gedit, Emacs).

It is an angular 5 project using yarn. It is composed of several angular UI-Components that are pulled in via dependencies in the `packages.json` and are colocated to this project.

The UI contains no business logic. All (non UI) functionality is realized through `REST` calls into the backend.

Technologies: angular 5, typescript

Supporting Technologies: nix, git, yarn, ng-packagr

## Test-Editor-Backend (REST services)

To locally setup the development environment, follow the setup section within the readme of the project [here](https://github.com/test-editor/test-editor-backend#setup-development).
Don't worry, it is setup in no time with just a couple of shell commands.
Prerequisite is an installation of linux with curl and git, all other dependencies are pulled by the respective shell.nix (using the nix package manager).

You can edit the project files (mostly [xtend](http://www.eclipse.org/xtend/)) with an IDE of your choice (e.g. Eclipse). If using Eclipse, please make sure to use photon for DSL and install `Buildship` for gradle integration. After `./gradlew eclipse` you can import the gradle project. Please make sure to reduce cyclic project dependency errors (which only eclipse sees) to warnings.

The backend project consists of two subprojects 
1. xtext backend (in org.testeditor.web.backend.xtext), providing language and index `REST` endpoints
2. persistence backend (in org.testeditor.web.backend.persistence), providing persistence and test execution `REST` endpoints

Technologies: java 10, xtend, dropwizard

Supporting Technologies: nix, git, gradle

## Test-Editor-Xtext-Gradle (Languages)

To locally setup the development environment, follow the setup section within the readme of the project [here](https://github.com/test-editor/test-editor-xtext-gradle#setup-development).
Don't worry, it is setup in no time with just a couple of shell commands.
Prerequisite is an installation of linux with curl and git, all other dependencies are pulled by the respective shell.nix (using the nix package manager).

You can edit the project files (mostly [xtend](http://www.eclipse.org/xtend/) and [xtext](http://www.eclipse.org/xtext/)) with an IDE of your choice (e.g. Eclipse). If using Eclipse, please make sure to use photon for DSL and install `Buildship` for gradle integration. After `./gradlew eclipse` you can import the gradle project. Please make sure to reduce cyclic project dependency errors (which only eclipse sees) to warnings.

The language project consist of a quite a lot of subprojects which are described in more detail in the project [readme](https://github.com/test-editor/test-editor-xtext-gradle#project-overview).

Technologies: java 10, xtend, xtext

Supporting Technologies: nix, git, gradle
