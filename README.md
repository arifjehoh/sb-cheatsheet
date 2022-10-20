# Spring Boot - Cheatsheet
This repository is a collection of Spring boot code snippes to help with implementation of logic.

## Maven repository
[Maven repository](https://mvnrepository.com), used for fetching the latest dependency.

## Application`.properties` to `.yaml`
1. Navigate to resource directory.
2. Change `application.properties` to `application.yaml`.

## Custom Banner in log window
1. Browse [Text to ASCII](http://patorjk.com/software/taag/#p=display&f=Standard&t=Spring%20Boot%0A)
2. Enter your text in the text box.
3. Create a `banner.txt` file in resource directory.
4. Copy content to `banner.txt`.

## Web
Under this section will be a collection of code snippets for developing web project.

### RESTful API
```java
@RestController
@RequestMapping(path = "")
public class Controller {
    
    // TOOD add content
    
}
```
GET endpoint snippet.
```java
@GetMapping(path = "")
public Object methodName() {
    return object;
}
```
