---
layout: page
title: "Tutorial: test case \"create hero\""
permalink: /te_markdown/heroes-create-testcase/
---

Estimated reading time: 8 minutes

Test cases implement test specifications. They are executable and are therefore more strict on syntax than test specifications are. The vocabulary that is used within these
test cases are largely controlled by the user of the test editor, however, sane defaults are provided.

## How do I write test cases?

The software under test that is used for this example is an implementation of the heroes tutorial of the angular framework (see [here](https://angular.io/tutorial)).

You want to know more about the software that is tested here? [read more](/te_markdown/sut-heroes){:class="web-button-grey reduced-padding"}

The test specification that is implemented in this example is described in detail in this [tutorial](/te_markdown/heroes-create-spec).

Given you have a running instance of the test-editor-web (see [here](/te_markdown/local-setup)), the following steps are necessary to implement the test specification.
- navigate to (or create) the folder to hold the test case
 - create a new file with the extension '.tcl' (e.g. CreateHero.tcl) by clicking the new file button on the left corner of the [Test-Navigator](/te_markdown/terminology#test-navigator). Hit the  ```RETURN``` key on your keyboard to create the file.

![screencase: create test case file](/images/tutorial/tutorial.heroes.create.testcase.1.create-file.gif "screencast: create test case file")

- Write the test case name into the opened editor, prefixing it with '#' (e.g. '# CreateHero')
- State that this test case implements the `CreateHero` specification ('implements CreateHero' in the same line)
- Notice the yellow warning icon on the left of the editor in the first line, it indicates that your mentioned specification is not implemented yet.

![screencase: name test case](/images/tutorial/tutorial.heroes.create.testcase.2.enter-name.gif "screencast: name test case")

- Copy the specification steps of the test specification (all three lines starting with '*') and the warning will dissapear.

![screencase: copy specification](/images/tutorial/tutorial.heroes.create.testcase.3.copy-tsl.gif "screencast: copy specification")

- Now implement each specification step with the actual test flow intended

  - `* Given: I am on the heroes page`
```
        Component: org.testeditor.fixture.web.WebBrowser
        - Start <Firefox>
        - Browse "http://sut:4200/heroes"
```

![screencase: enter given](/images/tutorial/tutorial.heroes.create.testcase.4.enter-given.gif "screencast: enter given")

  - `* When: I create a hero named "Sancho"`
```
        Component: org.testeditor.heroes.Heroes
        - Wait "2" seconds until <Add> is found
        - Click <Add>
        - Enter "Sancho" into <Name>
        - Wait "2" seconds until <Save> is found
        - Click <Save>
```

![screencase: enter when](/images/tutorial/tutorial.heroes.create.testcase.5.enter-when.gif "screencast: enter when")

  - `* Then: The hero should be the last one of the list`
  ```
        Component: org.testeditor.heroes.Heroes
        - Wait "2" seconds // until page is fully rendered after save
        - actualName = Read <LastHero>
        - assert actualName = "21 Sancho"
```

  - and finally do some cleanup (closing the browser)
```
        Component: org.testeditor.fixture.web.WebBrowser
        - Close browser
```


![screencase: enter then](/images/tutorial/tutorial.heroes.create.testcase.6.enter-then.gif "screencast: enter then")

That's it. Your first test in place. 

Do you want to know how to execute your test? 
[read more](/te_markdown/heroes-create-testcase-execution){:class="web-button-grey reduced-padding"}

Do you want to learn more about the editor and how the tests can be written, saved or making use of content completion etc.?
[read more](/te_markdown/heroes-create-testcase-editor){:class="web-button-grey reduced-padding"}

## Some reflections

The test case is expected to be written by a tester before the application is in place. The function of a test case is manifold.

* It represents a concrete test execution plan that implements a test specification and can be readily understood by the domain expert who wrote the specification
* It is concrete insofar as to be executable 
* It is the concrete and detailed expectation developers can realize their application for
* It functions as a bridge between actual feature implementation (developer) and feature specification (domain expert), working as an artifact for discussion between domain expert, tester, and developer

It is quite common to have the test case change because of implementation issues that could not have been foreseen. Changes need to be discussed though, which again has the benefit of sharing a common understanding of the feature to be implemented between domain expert, tester and developer. 

The vocabulary used in test cases is largely defined through artifacts written in the application mapping language (AML). The tester/developer writes mappings of the test vocabulary onto the actual implementation using this AML.
For the given tutorial a minimal AML was provided (Heroes.aml), partially describing the software under test.

Do you want to learn more about the AML?
[read more](/te_markdown/heroes-create-aml){:class="web-button-grey reduced-padding"}
