# Read: Class 11 Read: 11 - Spring

## Spring App Basics


1. build an application that has a static home page and that will also accept HTTP GET requests
1. It will respond with a web page that displays HTML. The body of the HTML will contain a greeting: “Hello, World!”
1. You can customize the greeting with an optional name parameter in the query string. The URL might then be <http://localhost:8080/greeting?name=User>
1. Used [Spring Initializr](https://start.spring.io/) to initialize a new spring project
1. In Spring’s approach to building web sites, HTTP requests are handled by a controller `@Controller`
1. The `@GetMapping` annotation ensures that HTTP GET requests for example to /greeting are mapped to the `greeting()` method.
1. `@RequestParam` binds the value of the query string parameter into the parameter of the greeting() method.
1. This query string parameter is not required. If it is absent in the request, the defaultValue of World is used.
1. @SpringBootApplication is a convenience annotation that adds all of the following:
   - `@Configuration`: Tags the class as a source of bean definitions for the application context.
   - `@EnableAutoConfiguration`: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.
   - `@ComponentScan`: Tells Spring to look for other components, configurations, and services in the com/example package, letting it find the controllers.
1. The main() method uses Spring Boot’s SpringApplication.run() method to launch an application.

### Build an executable JAR

1. Building an executable jar makes it easy to ship, version, and deploy the service as an application throughout the development lifecycle, across different environments, and so forth.

### RUN

1. gradle: `./gradlew bootRun`
1. build the JAR file by using `./gradlew build` and then run the JAR file by `java -jar target/gs-serving-web-content-0.1.0.jar`

### Add a Home Page

1. Spring Boot serves static content from resources in the classpath at /static (or /public). The index.html resource is special because, if it exists, it is used as a "`welcome page
## Spring MVC and Thymeleaf
### Spring model attributes
1. Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes. The equivalent term in Thymeleaf language is context variables.
1. How to add model attributes to a view in Spring MVC
   - Add attribute to `Model` via its `addAttribute` method:
   - Return `ModelAndView` with model attributes included:
   - Expose common attributes via methods annotated with `@ModelAttribute`:
1. You can access model attributes in views with Thymeleaf as follows:
```HTML
<tr th:each="message : ${messages}">
    <td th:text="${message.id}">1</td>
    <td>
        <a href="#" th:text="${message.title}">Title ...</a>
    </td>
    <td th:text="${message.text}">Text ...</td>
</tr>
```
### Request parameters

1. In order to access the q parameter in `https://example.com/query?q=Thymeleaf+Is+Great!` you can use the param prefix `<p th:text="${param.q}">Test</p>`
1. If you access multivalued parameter with ${param.q} you will get a serialized array as a value.

### Session attributes

1. Similarly to the request parameters, session attributes can be accessed by using the session. prefix `<p th:text="${session.mySessionAttribute}" th:unless="${session == null}">[...]</p>`

### ServletContext attributes

1.  In order to access ServletContext attributes in Thymeleaf you can use the #servletContext. prefix

```html
<table>
  <tr>
    <td>My context attribute</td>
    <!-- Retrieves the ServletContext attribute 'myContextAttribute' -->
    <td th:text="${#servletContext.getAttribute('myContextAttribute')}">42</td>
  </tr>
  <tr th:each="attr : ${#servletContext.getAttributeNames()}">
    <td th:text="${attr}">javax.servlet.context.tempdir</td>
    <td th:text="${#servletContext.getAttribute(attr)}">/tmp</td>
  </tr>
</table>
```
### Spring beans
1. Thymeleaf allows accessing beans registered at the Spring Application Context with the @beanName syntax
1. @urlService refers to a Spring Bean registered at your context `<div th:text="${@urlService.getApplicationUrl()}">...</div>`

```java
    @Configuration
        public class MyConfiguration {
            @Bean(name = "urlService")
            public UrlService urlService() {
                return () -> "domain.com/myapp";
            }
        }
        public interface UrlService {
            String getApplicationUrl();
        }
```