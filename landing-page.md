LOGO

# Test-Editor-Web
  
  "UA Tests as they were meant to be"
  
  It is designed to bridge the gap between domain experts, testers and developers with a modern application that integrates with container
  technologies. It is dedicated to automate the tip of the testing pyramid (acceptance tests) to enable automated product releases and
  provide confidence in reliable product operation.
  
# Test First

  Write test specifications before the actual feature is implemented. Make your tests an integral element of your agile feature development.
    
  Write your first test specification in 5 minutes (link)
  What are test specifications for? (link)

   this text is on the next page
   - With test specifications the domain expert expresses what he expects the test to verify
   - The test specification functions as communication basis between domain expert, tester and developer
   - Test specifications are implemented by a testers in concrete test cases
   - The domain expert can read, validate and execute test cases based on the specification previously written
    
# For Domain Experts

  Use a language designed for tests which is designed to be used by domain experts. Define the vocabulary and abstractions of your tests
  yourself and specify readable, comprehensible and reusable tests.
  
  Write your first test case in 5 minutes (link)
  What are test cases? (link)
  
  this text is on the next page
  - Tests or test cases are executable test descriptions that implement a test specification
  - They are written in a language that is largely designed by the tester
     
        * Create a hero named "Sancho"
        Component: MyHeroes
        - Enter "Sancho" into <Name>
        - Press <Add>
        
# Multiple Test Drivers
  Test different technologies, from web applications up to mainframe applications.
  Use the Test-Editor-Web to test your application, regardless on which technological platform it runs.

  Fixtures (link)

  this text is on the next page
  Web-Fixture (html5, angular): Allows you to test contemporary web applications with firefox or chrome
  Rest-Fixture: Allows to test rest services using json data to drive them
  Swing-Fixture: Allows to test java swing applications
  Host-Fixture (mainframe): Allows to test mainframe programs through 3270 terminal emulation
   
# Containered Test Execution

  Have automated test executions that run locally exactly as they run in the cloud.
  Test execution is performed within docker containers that are isolated and complete such that the identical container is used locally as it is used in the cloud.

# Web UI

  Make use of a feature rich editor without the need of local installations. Specify and run your tests without the need of a fat client.
    
  The Test-Editor-Web frontend is an angular application served through an nginx web server from a docker container. All the user of the
  Test-Editor-Web needs is a contemporary browser. There is no need for any additional local installation.
  
# Seamlessly integrate into your CI
  Integrate your tests into existing CI pipelines without any hassle.
