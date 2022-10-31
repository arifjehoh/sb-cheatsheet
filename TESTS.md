# Collections of Test
Code snippets to help with Writing better tests.
Using JUnit5.

## Extension Class
```java
@ExtendWith(SpringExtension.class)
@SpringBootTest(classes = Main.class)
@WebAppConfiguration
public abstract class AbstractTest {
    protected MockMvc mockMvc;

    private final WebApplicationContext context;

    public AbstractTest(WebApplicationContext context) {
        this.context = context;
    }
    
    // ...
    
}
```
This class is used to extend for testing the integration layer, mapping entity to json, and json to entity.

```java 
// AbstractTest Class
protected void setup() {
    mockMvc = MockMvcBuilders.webAppContextSetup(context).build();
}
```
```java
// Test Class
@BeforeEach
void setUp() {
    super.setup();
}
```
This class is run in the integration test class, in the method `setUp`.

```java
// Abstract Class
protected String toJson(Object entity) throws JsonProcessingException {
    ObjectMapper objectMapper = new ObjectMapper();
    return objectMapper.writeValueAsString(entity);
}
```
```java
// Test Class
super.toJson(body);
```
This method is converting an object to json format to matched with `content-type=application/json`.

```java
// Abstract Class
protected <T> T fromJson(String entity, Class<T> target) throws JsonParseException, IOException {
    ObjectMapper objectMapper = new ObjectMapper();
    return objectMapper.readValue(entity, target);
}
```
```java
// Test Class
super.fromJson(body, TARGET_CLASS.class);
```
This method is converting an json to object format, matched with `content-type=application/json`.
