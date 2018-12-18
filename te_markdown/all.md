---
layout: page
title: 
permalink: /te_markdown/all/
---

<a name="test-first"></a>

##  ![GitHub](/images/test_first_icon.svg?sanitize=true){: style="width: 40px; height: 40px"} Test First
Estimated reading time: 3 minutes

 ![Writing a Test Specification](/images/testfirst.gif "Writing a Test Specification"){: style="    display: block; margin-left: auto; margin-right: auto; width: 60%;" }

In agile development, *domain experts* write user stories with explicit *acceptance criteria* that are used to guide *developers* during implementation, and to decide when the story is completed. To avoid delays due to misunderstandings, acceptance criteria should be rigidly defined to leave no room for ambiguities, and facilitate continuous testing from inception to completion, to drive incremental development.

**Test-Editor-Web** fosters the collaboration of domain experts, testers, and developers by providing each group with the right tool for their job:

| Domain experts use the *test specification language* (TSL) to formalize desired system behaviors, using their own, domain-specific terminology, and thus requiring no technical expertise. Test specifications function as communication basis between domain experts, testers, and developers. | Testers implement test specifications using the *test case language* (TCL), yielding test cases that are formal enough to be executed automatically, while still being expressed in non-technical language, so that domain experts can read and validate them against their specifications. | Developers use the test specification as blueprint for implementation, and rely on the test cases to continuosly validate that they are making progress towards the intended goal.|
| ![Writing a Test Specification](/images/type-create-tsl.gif "Writing a Test Specification") | ![Writing a Test Case](/images/type-create-tcl.gif "Writing a Test Case") | ![Executing a Test Case](/images/execute-create-tcl.gif "Executing a Test Case") |
{: style="table-layout: fixed; border: 0px" }

The test-first practice, enabled by Test-Editor-Web on the user acceptance level, ensures that the development process is on the right track from the very beginning. Its ability for automated test execution allows to continuously validate each increment against the specification, so that development stays on track until completion.

#### Learn More

* [Test Your Domain](#test-domain): Discover the power and customizability of the different languages offered by Test-Editor-Web.


#### Try it for Yourself

* Do you want to write your first test specification in 5 minutes? [read more](/te_markdown/heroes-create-spec){:class="web-button-grey reduced-padding"}


<br>

___


<br>

<a name="test-your-domain"></a>
## ![GitHub](/images/your_domain_icon.svg?sanitize=true){: style="width: 40px; height: 40px"} Test Your Domain
 

Estimated reading time: 3 minutes

 ![Test your domain](/images/testcase_typing.gif "Test your domain"){: style="    display: block; margin-left: auto; margin-right: auto; width: 60%;" }

User acceptance testing is a collaborative activity involving domain experts, testers, and developers. Therefore, effective and efficient tools have to address the different needs of each of these roles. In particular, they must not expose technical aspects that would shut out less tech-savvy users that nevertheless need to participate in the process. 
For example, tools embedded into heavy-weight integrated development environments expose far too many unneeded features and capabilities that distract from the task at hand, and unnecessarily steepen the learning curve. The same is true for using existing general-purpose programming languages to express test specifications and test cases, that were not build with these use cases in mind.

**Test-Editor-Web** is designed specifically so that domain experts are empowered to write testable specifications, without requiring deep technical knowledge.

To this end, the languages used to express test specifications and test cases are tailored specifically towards their respective use cases. They have been purpose-built from scratch, as opposed to extending an existing programming language, so that no unneeded and potentially confusing concepts are exposed, allowing to express test specification and test cases in a clear and concise manner. 

At the same time, the languages are *customizable*, so that concepts from the application domain and the software under test can be defined and given semantics to be used directly in tests, making them more natural to read and easier to understand for domain experts.

~~~
* Create a hero named "Sancho"
Component: MyHeroes
- Enter "Sancho" into <Name>
- Press <Add>
~~~

Furthermore, the user interface has been kept clear and reduced to the essential features that help users with their tasks. Domain experts, testers, and developers can use filters to further focus their view with respect to their respective tasks and expertise.

#### Learn More

* [Test Your Application](#test-application): Read about Test-Editor-Web's capabilities to target different application technologies.


#### Try it for Yourself

* Do you want to write your first test specification in 5 minutes? [read more](/te_markdown/heroes-create-spec){:class="web-button-grey reduced-padding"}
* Do you want to Write your first test case in 8 minutes? [read more](/te_markdown/heroes-create-testcase){:class="web-button-grey reduced-padding"}


<br>

___


<br>

<a name="test-application"></a>
## ![GitHub](/images/your_application_icon.svg?sanitize=true){: style="width: 40px; height: 40px"} Test Your Application

Estimated reading time: 3 minutes

 ![Writing a Test Specification](/images/applications_a.gif "Writing a Test Specification"){: style="    display: block; margin-left: auto; margin-right: auto; width: 40%;" }

User acceptance tests should focus on the needs and expected behaviors of the software under test from a user-centric perspective, expressed in technology-agnostic terms of the application domain. However, to automate these tests, the particular technology stack of the software under test have to be taken into account. Effective user acceptance test tools have to cater to both requirements, while also being generic enough to be applicable to the testing of different applications build on diverse platforms and technologies.

**Test-Editor-Web** decouples test specification and test case descriptions from concrete, executable tests that can be run against a given software under test. From test cases expressed with the test case language (TCL), the actual test code is generated on demand, relying on different *test fixtures* that encapsulate the mapping of generic test steps to concrete actions appropriate for a particular technology. Out of the box, the following fixtures are available:

 * Web Fixture: Allows to test contemporary *web applications* (HTML5 in general, with particular support for *Angular* applications) with Firefox or Chrome.
 * REST Fixture: Allows to test *REST services* using JSON data to drive them.
 * Swing Fixture: Allows to test *Java Swing* applications.
 * Host Fixture: Allows to test mainframe programs through *3270 terminal emulation*.

Test-Editor-Web is extensible in this respect, and additional test fixtures can be implemented and added to address target platforms that are not yet covered.

#### Learn More

* [Test Containerized](#test-containerized): Find out about the ability and benefits of executing tests in dedicated Docker containers.


#### Try it for Yourself

* Do you want to write your first test specification in 5 minutes? [read more](/te_markdown/heroes-create-spec){:class="web-button-grey reduced-padding"}
* Do you want to Write your first test case in 8 minutes? [read more](/te_markdown/heroes-create-testcase){:class="web-button-grey reduced-padding"}


<br>

___


<br>

<a name="test-containerized"></a>
## ![GitHub](/images/containerized_icon.svg?sanitize=true){: style="width: 40px; height: 40px"} Test Containerized

Estimated reading time: 2 minutes

 ![Test containerized](/images/containerized.gif "Test containerized"){: style="    display: block; margin-left: auto; margin-right: auto; width: 60%;" }

User acceptance tests, like any automated tests, should be repeatable, with reproducible test results. For that, it is important that tests run in a controlled environment that shields them from unwanted influences of the surrounding execution platform, and from interference with other tests.

**Test-Editor-Web** encapsulates test runs in a Docker container, which provides a high degree of both isolation from outside influences, as well as great control over the test environment inside. The containerization further imparts a high degree of flexibility in terms of deployment, allowing tests to be run virtually anywhere, and at scale. The same container is used locally as it is used in the cloud.

![screencast: execute test case](/images/tutorial/tutorial.heroes.create.testrun.gif "screencast: execute test case")


#### Learn More

* [Test in Your Browser](#test-browser): See the advantages of the Test-Editor-Web being delivered through the browser.


#### Try it for Yourself

* Do you want to write your first test specification in 5 minutes? [read more](/te_markdown/heroes-create-spec){:class="web-button-grey reduced-padding"}
* Do you want to Write your first test case in 8 minutes? [read more](/te_markdown/heroes-create-testcase){:class="web-button-grey reduced-padding"}


<br>

___


<br>

<a name="test-browser"></a>
## ![GitHub](/images/your_browser_icon.svg?sanitize=true){: style="width: 40px; height: 40px"} Test in Your Browser

Estimated reading time: 2 minutes

 ![Test in your Browser](/images/your_browser.gif "Test in your Browser"){: style="    display: block; margin-left: auto; margin-right: auto; width: 80%;" }

Testing, on any level, is an indispensible quality assurance measure, yet is often neglected. Therefore, it is all the more important that the entry barrier to adopt a user acceptance test tool is as low as possible, both from the end user's perspective, as well as for maintainers and administrators providing technical support. Desktop applications require users to install them on their own machines, and may present administrators with the challenge of providing the latest updates.

**Test-Editor-Web** lives in the browser: once deployed, users can just be given a URL to type into their browser's address bar and start creating tests – no need to install anything. When updates do become available, administrators can deploy them centrally; users do not have to take action, at all, and will just be presented with the latest version, the next time they open it.

#### Learn More

* [Test Continuously](#test-continuously): Learn about embedding user acceptance tests into your continuous integration process.

#### Try it for Yourself

* Do you want to write your first test specification in 5 minutes? [read more](/te_markdown/heroes-create-spec){:class="web-button-grey reduced-padding"}
* Do you want to Write your first test case in 8 minutes? [read more](/te_markdown/heroes-create-testcase){:class="web-button-grey reduced-padding"}

<br>

___


<br>

<a name="test-continuously"></a>
## ![GitHub](/images/continuously_icon.svg?sanitize=true){: style="width: 40px; height: 40px"} Test Continuously

Estimated reading time: 2 minutes

 ![Test continuously](/images/ci.gif "Test continuously"){: style="    display: block; margin-left: auto; margin-right: auto; width: 100%;" }

Modern, agile development practices encompass continuous integration, delivery, and deployment. User acceptance testing should be a part of these processes, to monitor progress while developing with each increment and complement existing quality assurance measures. Therefore, the tests have to be integrable into the corresponding build pipelines.

**Test-Editor-Web** allows to both start test runs directly from within the web-based user interface, but also to execute them completely independent. Tests can therefore be easily made part of automated build processes to be run either locally or within the context of a CI-server. Technically, this option is provided through the [Gradle](https://gradle.org/) build automation system.

#### Try it for Yourself

* Do you want to write your first test specification in 5 minutes? [read more](/te_markdown/heroes-create-spec){:class="web-button-grey reduced-padding"}
* Do you want to Write your first test case in 8 minutes? [read more](/te_markdown/heroes-create-testcase){:class="web-button-grey reduced-padding"}
