### JUnit Annotations
 - `@Test`: Marks a method as a test.
 - `@BeforeEach`: Method to be executed before each test.
 - `@AfterEach`: Method to be executed after each test.
 - `@BeforeAll`: Static method to be executed before all tests.
 - `@AfterAll`: Static method to be executed after all tests.
 - `@Disabled`: Disables a test.

Annotated Test Life cycle

![[Test Annotations.png]]


@BeforeAll

Executed once before all tests. Ideal for global configurations that are required before any tests are run. It must be a static method.

 ``` Java
 @BeforeAll
 static void setupAll() {
	 // Global configuration
 }
 ```

@BeforeEach

Executed before each test. Used to configure the initial state required for each test individually.

 ```Java
 @BeforeEach
 void setup() {
	 // Configuration before each test
 }
 ```

@Test

Test method. Marks the method as a test that will be executed by JUnit.

 ```Java
 @Test
 void testMethod() {
	 // Test code
 }
```

@AfterEach

Executed after each test. Used to clear or reset the state after each test, ensuring that one test does not affect the other.

```Java
@AfterEach
void tearDown() {
	// Cleanup after each test
}
```

@AfterAll

Executed once after all tests. Ideal for freeing up global resources or carrying out final cleaning tasks. It must be a static method.


``` Java
@AfterAll
static void tearDownAll() {
	// Global cleaning
}
```