# Do Not Mix Perforance and Integration Tests

# Table of Contents
- [Acronyms](#acronyms)
- [Introduction](#introduction)
- [Differences between performance and end to end tests](#past-learnings---using-jmeter-for-e2e-tests)
- [Past Learnings - Using Jmeter for E2E tests](#compare-bdd-frameworks)
- [E2E with BDD](#e2e-with-bdd)
- [Compare BDD frameworks](#compare-bdd-frameworks)
- [Conclusion](#conclusion)
- [References](#references)

## Acronyms

|Acronym|Meaning|
|----|---|
|E2E|	End to End tests|
| BDD	 | Behavior-driven Development |
| DSL	| Domain-Specific Language|
| TPS |	Queries or Transaction per Second for API|


## Introduction

Performance test and E2E tests have a different purpose.

Most of java based microservices mix performance tests and end to end integration tests. Actually these two tyoe of tests have different purposes.

Generally we use JMeter for both type tests.
JMeter is a performance testing tool and using it for integration tests is wrong.

## Differences between performance and end to end tests 

|Performance Test | Integration Tests|
|-------|------------|
| Used to measure response time, error rates by increasing concurrent users over time.<br>It should simulate real-time system load. <br>example say 10 TPS for 15 min, 20 TPS for 5 min till API breaks.<br>The purpose is to measure the latency and error rate of API.|Used to check the correctness of major functional requirements of API.<br>It should be run with a single user. <br>The purpose is to check functionality. |
|It is recommended to only assert minimum things like response status.|	It is recommended to check response status plus response body and assert on that.|
| These tests should not contain negative tests like checking 4XX and 5XX errors.|	These tests should container 2XX, 4XX, 5XX errors for main scenarios.|
|Maintained by developers |	maintained by developers  and product managers |
| Performance tests may not need special creation of data other than user creation <br>Should not contain the use of test APIs it should be as realistic as possible.| Need to create data and clean up after the tests.<br>May contain the use of test API or tools or scripts.|
| They should not contain mocks. | May contain mocks. |
| It should not have wait/sleep loops or think time etc. <br>They should run and build load as fast as possible.|	It might have to think time  or waits to mock actual users of API|
| The right tools are : <br>Real-Time API (RTAPI) Latency Testing Tool<br>Apache JMeter |The right tools are:<br>BDD based frameworks<br>[BDD: Spock](http://spockframework.org/)<br>[BDD Cucumber](https://cucumber.io/)|

BDD is the right tool for writing API automation tests.

# Past Learnings - Using Jmeter for E2E tests
In past, while developing java based micro-services, we have moved all e2e tests out of Jmeter.

Following are problems for using Jmeter for e2e testing

- No good way to assert responses and debug in case of problems
- Not possible to re-use steps in tests 
- The product manager and developer can not understand  e2e tests 
- Difficult to review changes in tests

## In general, Jmeter has the following problems 

#### Learning Curve 
- It has a learning curve to understand the main components, using from command line/UI and debugging. 
Checking correctness
- it is difficult to debug in case of problems 
- It has limited support examples like JSON parsing which needs additional special plugins and that needs additional setup.
- Difficult to assert dynamic response as need groovy script to check
####  Readability and Maintainability
- Difficult to maintain as it needs UI client to see exact tests
- It needs an understanding of Jmeter components for both developer and reviewer 
#### Extensibility 
- It is challenging to externalize the configurations in the file outside Jmeter.
- Multiple disparate scenarios need multiple Jmeter test scripts 
#### Change management 
Change management is difficult as we can not review diff in source code management system 
#### Reusability 
- It is difficult to reuse the steps, we can refer to step in testing as we have only the option to clone it,  in case of changes, we have to update all steps.

## E2E with BDD

BDD is the right tool for the E2E test of API or system because it is the common language between product manager, developer, and testers.

The main idea is whenever a major epic is asked to develop there should be a corresponding  E2E test written first either by the product manager or developer so that system behaves as per expectation.

### Compare BDD frameworks

You can use any framework to test REST API written in any language.
Following compasirion assume that your current micro-service is using java stack. 

| Framwork | Language | Pros | Cons|
|----------|----------|----------|----------|
| [Spock](http://spockframework.org/) | 	groovy  | groovy is a JVM language and easy to learn for Java developers.<br>You can call java code from groovy.<br> Feature, scenario, and code reside side by side.<br>You can import published java clients/request response for compile time check.| NA |
| [Cucumber](https://cucumber.io/) | 	java	|You can import published java clients/request response for compile time check.|  Feature, the scenario text file is separate.<br>Java code is mapped to features and scenarios.<br>Java is not a friendly language for BDD specific DSL.|
| [ginkgo](https://github.com/onsi/ginkgo) | 	golang	 | Support for gRPC/protobuf if used internal API | The learning curve for the team with java stack<br> If microservice does not publish golang client then no checks for contract| 
| [pytest-bdd](https://github.com/pytest-dev/pytest-bdd) | 	python	| Support for gRPC/protobuf if used internal API.| Less code <br>easy to write<br>If microservice does not publish python client then no checks for contract |
| [jest-cucumber](https://github.com/bencompton/jest-cucumber)	|jest,<br> node.js<br>typescript| Less code <br>easy to write| If microservice does not publish node js client then no checks for contract  or re-use|

## Conclusion

Spock is a good candidate for E2E testing of microserivces with java srtack with the aspects described above by comparing with other existing BDD frameworks.

## References

- [Behavior Driven_Development](https://en.wikipedia.org/wiki/Behavior-driven_development)

- [Cucumber Rest API Testing](https://www.baeldung.com/cucumber-rest-api-testing)
