### Assertions
 - `assertEquals(expected, actual)`: Checks if the values ​​are equal.
 - `assertTrue(condition)`: Checks if the condition is true.
 - `assertFalse(condition)`: Checks if the condition is false.
 - `assertThrows(exceptionClass, executable)`: Checks whether an exception is thrown.
 - `assertAll(executables)`: Groups multiple checks.

### Exemplo Simples

Aqui está um exemplo de um teste unitário simples usando alguns dos conceitos acima:

```java
import org.junit.jupiter.api.*;

import java.util.ArrayList;
import java.util.List;

import static org.junit.jupiter.api.Assertions.*;

class MyServiceTest {

    private MyService myService;
    private List<String> data;

    @BeforeEach
    void setUp() {
        myService = new MyService();
        data = new ArrayList<>();
        data.add("test1");
        data.add("test2");
    }

    @Test
    void testAddData() {
        myService.addData("test3");
        assertEquals(3, myService.getData().size());
        assertTrue(myService.getData().contains("test3"));
    }

    @Test
    void testRemoveData() {
        myService.addData("test3");
        myService.removeData("test3");
        assertEquals(2, myService.getData().size());
        assertFalse(myService.getData().contains("test3"));
    }

    @Test
    void testException() {
        Exception exception = assertThrows(IllegalArgumentException.class, () -> {
            myService.removeData("test3");
        });
        assertEquals("Data not found", exception.getMessage());
    }

    @AfterEach
    void tearDown() {
        data.clear();
    }
}

class MyService {
    private List<String> data = new ArrayList<>();

    public void addData(String str) {
        data.add(str);
    }

    public void removeData(String str) {
        if (!data.contains(str)) {
            throw new IllegalArgumentException("Data not found");
        }
        data.remove(str);
    }

    public List<String> getData() {
        return data;
    }
}
```

