---
layout: page
title: Overview and Terminology
permalink: /te_markdown/terminology/
---

Test-Editor is a lightweight application for specifying, implementing, and executing user acceptance tests, that lives in your browser. This page provides a high-level [overview](#overview) of its user interface and its central components. If you would rather like to jump right in and try out Test-Editor for yourself, have a look at one of the [quickstart tutorials](/te_markdown/tutorials). If any questions should arise, you may want to come back here to get your bearings by looking at the overview, or look up individual terms in the [glossary](#glossary) further down.

## Overview

![Overview](/images/te.overview.svg?sanitize=true){:class="img-responsive"}

In the screenshot above you can see the different areas of Test-Editor-Web, indicated in yellow.
In the following, each area is briefly described.

<a name="test-navigator">
### 1. Test Navigator
In this area you can specify the structure of the different test artifacts.
You can create, delete, rename, cut, copy, and paste test artifacts and refresh the workspace.
In addition you can filter the different test-artifacts, so that just the specific test-artifact is visible which was selected.

<a name="editor-area">
### 2. Editor Area
This area is the place to write different test artifacts. The editor supports you with a content completion of the different possibilities during typing and saving your test case, e.g. through the shortcut ```CTRL + S```.

<a name="test-step-selector">
### 3. Test Step Selector
The Test Step Selector provides you with an overview of the test steps available for defining test cases.

<a name="test-execution-navigator">
### 4. Test Execution Navigator
Here you can execute the chosen test case by clicking the start button on the top left corner of this area. After test execution, the results of the individual test steps are indicated by either green (success) or red (failure) icons. In the latter case, details regarding the cause of the failure can be inspected in the _Test Execution Details_.

<a name="test-execution-details">
### 5. Test Execution Details
In this area, details about the test step selected in the _Test Execution Navigator_ are shown. In case of failures during execution, this area offers hints about what went wrong. The general sequence of events during test execution can be traced by accessing _logs_ and inspecting _screenshots_.


----

## Glossary

<a name="application-mapping"></a>Application Mapping
: A set of platform- or application-specific [test steps](#test-step), mapped to concrete actions to be performed for testing, that are implemented in [test fixtures](#test-fixture).

<a name="application-mapping-language"></a>Application Mapping Language (AML)
: A language used by [testers](#tester) to define the platform- or application-specific vocabulary for the [test steps](#test-step), and by [developers](#developers) to map these steps to the concrete actions to be performed for testing, implemented in [test fixtures](#test-fixture).

<a name="component"></a>Component
: A component is a container for UI elements and interactions. In case of a web application it could be used to describe a  single web page.

<a name="developer"></a>Developer
: A person who is involved in the development of the [software under test](#software-under-test). User acceptance tests described with the [test case language (TCL)](#test-case-language) are continuously executed during the development process to check the progress with each development increment, and to validate the implementation.

<a name="domain-expert"></a>Domain Expert
: A user of the [software under test](#software-under-test), or other stakeholder, who has a deep understanding of the problem domain. Domain experts specify what they expect the system to do and how it should behave, using the [test specification language (TSL)](#test-specification-language).

<a name="locator-strategy"></a>Locator Strategy
: Locating elements on the UI is described using locator types (for further information on locating web elements view this [Selenium documentation](https://www.seleniumhq.org/docs/02_selenium_ide.jsp#locating-elements)). The [web-fixture](https://github.com/test-editor/web-fixture) allows to choose locator types for web applications. Available locator types allow locating by XPATH, name, identifier, link text, CSS ([for further information see W3Schools CSS Tutorial](https://www.w3schools.com/css/default.asp)) or XPath ([for further information see W3Schools XPath Tutorial](http://www.w3schools.com/xml/xpath_intro.asp)).

<a name="software-under-test"></a>Software Under Test (SUT)
: The software system for which user acceptance tests are created by [testers](#tester). It is (going to be) used by [domain experts](#domain-expert), and implemented and maintained by [developers](#developer).

<a name="specification-step"></a>Specification Step
: A single step taken as part of a task to be performed with the [software under test](#software-under-test). Sequences of specification steps can form [test specifications](#test-specification).

<a name="test-artifact"></a>Test Artifact
: A file used by and / or created with the [Test-Editor-Web](#test-editor-web) for the overall purpose of user acceptance testing. In particular, these include files containing [test specifications](#test-specification), [test cases](#test-case), and [application mappings](#application-mapping) [test case language (TCL)](#test-case-language).

<a name="test-case"></a>Test Case
: A user acceptance test defined in terms of a sequence of [test steps](#test-step) to be executed, and expressed using the [test case language (TCL)](#test-case-language).

<a name="test-case-language"></a>Test Case Language (TCL)
: A language used by [testers](#tester) to implement [test cases](#test-case) conforming to [test specifications](#test-specification), by defining the necessary, concrete [test steps](#test-step) for automatic execution. See [this tutorial](/te_markdown/heroes-create-testcase/) to learn about writing test cases with TCL.

<a name="test-editor-web"></a>Test-Editor
: An application dedicated to automate the tip of the testing pyramid—acceptance testing—to enable automated product releases and provide confidence in reliable product operation. Designed to bridge the gap between [domain experts](#domain-expert), [testers](#tester), and [developers](#developer), Test-Editor is a modern application that integrates well with container technologies. See [Overview](#overview) for a description of its user interface components and functions, and [Tutorials](/te_markdown/tutorials) to learn about using it.

<a name="test-fixture"></a>Test Fixture
: A software library that implements concrete actions, specific to the platform and technology stack of a given [software under test](#software-under-test), to be performed during test execution. [Developers](#developer) use [application mappings](#application-mapping) to bind [test-steps](#test-step) to fixture logic. Out of the box, [Test-Editor-Web](#test-editor-web) comes with fixtures that enable the testing of _web_ applications, in particular _Angular_ applications, _REST_ services, _Java Swing_ applications, and mainframe applications through _3270 terminal emulation_.

<a name="test-specification"></a>Test Specification
: A usage scenario describing an interaction with the [software under test](#software-under-test), written by [domain experts](#domain-expert) to express desired system behaviors in a testable manner.

<a name="test-specification-language"></a>Test Specification Language (TSL)
: A language used by [domain experts](#domain-expert) to write [test specifications](#test-specification) of desired system behaviors. [Testers](#tester) refer to TSL [artifacts](test-artifact) when implementing them as [test cases](#test-case), using the [test case language](#test-case-language). See [this tutorial](/te_markdown/heroes-create-spec/) to learn about writing test specifications with TSL.

<a name="test-step"></a>Test Step
: A single, automatable step taken as part of a test executed against the [software under test](#software-under-test). In [test cases](#test-case) conforming to [test specifications](#test-specification), each [specification step](#specification-step) may be implemented by arbitrarily many test steps.

<a name="tester"></a>Tester
: A person responsible for user acceptance testing against the [software under test](#software-under-test). Testers write executable [test cases](#test-case) using the [test case language](#test-case-language) to implement [test specifications](#test-specification).
