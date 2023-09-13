# How to write a good unit test

A unit test is one that tests only a small part of the code and verifies its operation.

The size of the code to be tested varies according to the language and architecture, but in a simplified way, in object-oriented programming, a class or method can be seen as a unit.

Unit testing only checks functionality, that is, whether the program performs the expected actions in success scenarios and alternative flows. Checking communication, performance or any other characteristic is the role of other types of testing.

This is just a summary list of the main unit test writing practices and is organized in the form of mnemonics based on the book **Pragmatic Unit Testing in Java 8 with JUnit**.

## The basic

Simple, easy to understand, follows nomenclature, follows Arrange, Act, Assert pattern

## FIRST

###Fast

> Executes in a few milliseconds. Suite runs in 10 seconds or less!

To keep testing fast, maintain a **clean design**:

- Avoid calling code snippets that are slow; (pre-calculate)
- Refactor long methods;
- Instead of querying, receive values by argument (injection and inversion)

### Isolated

> Focuses on a small piece of code.

To keep the test isolated, remove the following dependencies:

- Calls to other systems;
- Calls to other **tests**;
- Code to be tested by calling other systems.

### Repeatable

> Finds the same results no matter how many times or how you run it.

For a test to be reproducible, the following dependencies must be removed:

- Response time. (if you are waiting for answers, it is not a unit test)
- Runtime. (runtime is performance test)
- External settings. (each test must do its own configuration)

### Self-validating

> Checks **alone** if things happened as expected.

To be independent of human interference it is necessary to automate:

- System configuration;
- Creation of test data;
- Cleaning resources impacted by the test;
- When the tests will be performed; (Infinitest + git hooks + CI Server)
- Maintaining good practices.

### Timely

It is written in time to make an impact on the code. (During development)

#### In old code

- Write tests immediately before refactoring;
- Select a SMALL section of code to refactor;

#### In new code

- Intersperse testing with development (even if TDD is not used);
- Reduce the amount of code written without tests.

## Right-BICEP

Right Right Results
B Boundary conditions
I Inverse relationship
C Cros-check results
E Error conditions
P Performance within bounds

### Right Results

Checks the happy path and ensures that the code does at least that path correctly.

It is the first test that must be guaranteed.

### Boundary conditions

Checks whether the limits of the value ranges (start and end) are respected, whether during data input or output.

Every data type is finite and each "field" has restrictions and ranges of valid and invalid values.

Values inconsistent with type = letters instead of numbers
Poorly formatted data = decimal places, spaces, punctuation
Overflow = operations that generate large numbers
Empty or null variables = Division by zero, null pointer, files that do not exist
Inconsistent lists = duplication, order
Chronological order of actions = Calls out of order, competition

### Inverse relationship

Checks whether the reverse operation undoes or brings a different result.

Sum Subtraction
Multiplication Division
Root Power
...

### Cros-check results

Check by other means whether the answer is correct.

We can use a different implementation to guarantee consistency, such as a lib from another software.

### Error conditions

Checks whether when forcing an error condition the program has an appropriate response.

Lack of memory
Lack of disk space
System clock changes
Network
Charge
Incompatibilities

### Performance within bounds

Checks if the code is within a reasonable limit

- New version is 2x slower
- Testing is 20% slower than average unit testing
- Test takes more than 800ms to execute

## CORRECT Boundary conditions

> Conformance, Ordering, Range, Reference, Existence, Cardinality, Time

### Conformance

The response conforms to some expected format.

### Ordering

The set of values is ordered or unordered as expected.

###Range

The value is within reasonable minimum and maximum limits

### Reference

The code must not make external references that are not under the direct control of the code.

### Existence

The value exists as expected (not null, non-zero).

### Cardinality

The number of values is exactly as expected.

### Time

Checks whether the actions are performed in the correct order and at the right time.

---
The importance of unit tests in improvement continues.

allows you to identify side effects
Facilitates refectoring

The importance of refactoring for unit tests

Generate concise test units

---

## References

LANGR, Jeff. **Pragmatic Unit Testing in Java 8 with JUnit**

NICOLETTE, Dave. **Continuous Unit Checking: Part Three**
https://www.leadingagile.com/2018/07/continuous-unit-checkingpart-three/

NIELSEN, Jakob. **Powers of 10: Time Scales in User Experience**
https://www.nngroup.com/articles/powers-of-10-time-scales-in-ux/

ONOFRIO, Thayse; LOURENÇO, Marilene. **Demystifying the software engineering test pyramid. Agile & other ways of working**
https://leaddev.com/agile-other-ways-working/demystifying-software-engineering-test-pyramid

SEEMANN, Mark. **TDD test suites should run in 10 seconds or less**
https://blog.ploeh.dk/2012/05/24/TDDtestsuitesshouldrunin10secondsorless/

VOCKE, Ham Vocke. **The Practical Test Pyramid**
https://martinfowler.com/articles/practical-test-pyramid.html
