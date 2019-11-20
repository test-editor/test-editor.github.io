---
layout: page
title: "Tutorial: Define Passwords"
permalink: /te_markdown/define-passwords/
---

Estimated reading time: 5 minutes

## Motivation

Often, applications under test require user credentials like username and password for user input. In order to avoid storing user information directly in the test case descriptions as plain text, viewable for all test participants, the Test-Editor offers the possibility to make this data available to test cases with following approaches. 


* The tester can specify variables inside the test case (variables must exist as environment variables in the test environment).

How to define these environment variable so that they may be used during the execution of test cases is described in the following chapter.

## How do I define credentials as environment variables?

There are several ways to set an environment variable in the Test-Editor:

* Definition of environment variables in the build.gradle file in the respective git user repository.
* Definition of environment variables directly in the system where the tests should run (Jenkins, Docker, etc.)


### Defining environment variables in build.gradle file 

The following section should be included in the build.gradle file in the repository where the test cases are stored. In our Hero Tutorial for creating test cases [corresponding tutorial](/te_markdown/heroes-create-testcase) the repository with the build.gradle file resides at [GitHub](https://github.com/test-editor/language-examples/blob/tutorial/hero-create-testcase/build.gradle). After defining the variables in the build.gradle file, the environment variables are then available at start time of the test process. This method can be used in the initial creation of test cases, because the passwords defined in the build.gradle file can not be viewed by the users of the Test-Editor. However, it is possible that people who have access to the git repository where the testcases reside, can see the passwords in plain text in the build.gradle file. This situation is known and has already been recorded as a futre TODO. However, since the tests are mainly intended to run in the context of deployment pipelines, the variables should be stored in encrypted form on these systems where tests are executed.

```
// add environmental variables needed by the test (for any 'require <var-name>' in tcl)
tasks.withType(Test) {
    // User (Jon Doe)
    environment 'user', 'JonDoe'
    environment 'password', 'verySecret'
 }
```

### Defining environment variables in Jenkins
If the test execution environment is Jenkins, the environment variables should be set up using Jenkins Credential Manager to be ready for test execution.


### Defining environment variables in Docker
If Docker is available as a test execution environment, the environment variables should be encrypted and passed into the Docker container to be ready for test execution.

## Usage of sensitive data in tests

User information such as `user names` and `passwords` can be passed to the test case via external environment variables.

The usage of the keyword `"require"` specifies user information, which should be available to the test via comma-separated environment  variables. At the beginning of each start sequence of test-execution, the test case checks if the environment variables specified by the `require` keyword have been defined. If the specified environment variables are not available at the start sequence of the test, the test case aborts at this point without performing the test.

### Syntax for specifying expected environment variables

To use user credentials as environment variables which are defined in the test execution environment described above, the following Syntax is available to use in a test case. How to write a test case is described in the [corresponding tutorial](/te_markdown/heroes-create-testcase). 

```
require public user,password
```

With the keyword `require`, the test will only be executed if the following parameters are available as environment variables in the system where the tests will be executed.

There are two ways to define an environment variable

* public
* not public

The difference will be described in the following chapter.

#### Definition in test case files

##### Example test case 

```
import org.testeditor.fixture.web.angularjs.*
 
require public user,password
 
* Open browser
Component: WebBrowser
    - Start <Firefox>
    - Browse "https://www.instagram.com"
    - Wait "2" seconds
 
* Login
Component: LoginPage
    - Enter @user into <UserName>
    - Enter confidential @password into <Password>
    - Wait "1" seconds
    - Click <LoginButton>
    - Wait "2" seconds
 
* close browser
Component: WebBrowser
    - Close browser
```

in the above test case, the environment variable `"user"` is defined with the keyword `public` at the beginning of the test case, which means the variable, in this case its value, is visible in log files.

The environment variable `"password"` has no access restriction and is therefore `not public` and is not displayed in log files. This is the default approach on how to handle environment variables

#### Usage in test case files

After defining the user credentials as described in the example above, the variables can be used as input data with the prefix `@` like `@user` or `@password`. 

In the above test case example, the user name "JohnDoe" is entered in a field without special treatment and the password is entered in the password field via a special method "Enter confidential @password into ...". This ensures that the password is only shown encrypted in log files and not in plain text.

