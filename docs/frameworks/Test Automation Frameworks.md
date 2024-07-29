
A framework is a platform for developing software applications.  It provides a foundation on which software developers can build programs for a specific platform.

It may include predefined classes and functions that can be used to process input, manage hardware devices, and interact with system software. This streamlines the development process since programmers don't need to reinvent the wheel each time they develop a new application.

A test automation framework is a sеt of guidelines and a software framework to automate tеsts for software applications. These guidelines could include coding standards, test-data handling methods, object repositories, processes for storing test results, or information on how to access external resources.

They normally include: a testing DSL, a test discovery mechanism, a test executor and some sort of result reporting. More complete solutions also add features like: test data creation, stub and mocking helpers, configuration test and some sort of test execution grouping.

Each programming language¹ and level of tests has its own Test Automation Framework².

|             |               Java                |           Python           |            .NET            |                                         JavaScript                                         |                   Kotlin                   |                                                                        Bash                                                                         |
| ----------- | :-------------------------------: | :------------------------: | :------------------------: | :----------------------------------------------------------------------------------------: | :----------------------------------------: | :-------------------------------------------------------------------------------------------------------------------------------------------------: |
| Unit        |      [[JUnit]]<br>[[TestNG]]      | [[pytest]]<br>[[unittest]] |   [[NUnit]]<br>[[xUnit]]   |                          [Jest](https://github.com/facebook/jest)                          | [Kotest](https://github.com/kotest/kotest) | [shUnit2](https://github.com/kward/shunit2/)<br>[Bats](https://github.com/bats-core/bats-core)<br>[Bash Unit](https://github.com/pgrange/bash_unit) |
| Integration | [[Spring Test]]<br>[[Arquillian]] |                            |                            |                                                                                            |                                            |                                                                                                                                                     |
| Acceptance  |    [[Appium]]<br>[[selenium]]     | [[Appium]]<br>[[selenium]] | [[Appium]]<br>[[selenium]] | [[Cypress]]<br>[[Playwright]]<br> [SerenityJS](https://github.com/serenity-js/serenity-js) |         [[Appium]]<br>[[selenium]]         |                                                                     [[Appium]]                                                                      |

## Cross plataform

### UI and Acceptance Testing

- [Karate 🌐](https://github.com/intuit/karate) - Java and cross-platform - UI and service
- - JavaScript - Acceptance and Service test
- [Gauge 🌐](https://github.com/getgauge/gauge) - Multi language - BDD style test
- [Recheck 🌐](https://github.com/retest/recheck) - Java - Visual Regression
- [Recheck 🌐](https://github.com/retest/recheck-web) - Java - WebPage Visual regression 
- [Sikuli X1 🌐](https://github.com/RaiMan/SikuliX1) - Java - Desktop UI testing
- [Puppeteer 🌐](https://github.com/puppeteer/puppeteer) - Javascript


¹ These are the languages I know **AND** I'm able give advice on testing.
² There are other frameworks **I don't know** enough to recommend.


### BDD Testing

- [Behave](docs/frameworks/behave.md)
- [Cucumber](docs/frameworks/cucumber.md)
- [Jasmine](docs/frameworks/jasmine.md)
- [Shellspec 🌐](https://github.com/shellspec/shellspec) - BDD unit testing framework for bash, ksh, zsh, dash and all POSIX shells.

### Infrastructure testing

- [Terratest](docs/frameworks/terratest.md) - Terraform
- [ChefSpec 🌐](https://docs.chef.io/workstation/chefspec/) - Chef
- [RSpec Puppet 🌐](https://rspec-puppet.com/) - Puppet
- [Pytest-Testinfra 🌐](https://github.com/pytest-dev/pytest-testinfra) - Python - Unit tests for infrastructure
- [ServerSpec 🌐](https://serverspec.org/)
- [Goss 🌐](https://github.com/aelsabbahy/goss) - Golang - Server Spec testing

### Architecture testing

- [`ArchUnit`](https://www.archunit.org/) - Java - A Java architecture test library to specify and assert architecture rules.

## Tools

- [PDF Compare 🌐](https://github.com/red6/pdfcompare) - Java - A PDF testing helper
- [Py Thruth 🌐](https://github.com/google/pytruth) - Python - Assertions for python tests.

## [[Fixtures]]

A software test fixture (also called "test context") is used to set up system state and input data needed for [test](https://en.wikipedia.org/wiki/Software_testing "Software testing") execution.


## References

techterms.com/definition/framework

smartbear.com/learn/automated-testing/

smartbear.com/learn/automated-testing/test-automation-frameworks/

smartbear.com/learn/automated-testing/best-practices-for-automation/

lambdatest.com/blog/best-test-automation-frameworks/

