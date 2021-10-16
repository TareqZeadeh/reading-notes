# Spring Security

## Authentication and Access Control

- The security of an application can be divided into two main portions:
    - Authentication : To determine if a user is authenticated.
    - Authorization : What an authenticated user is allowed to do.

### Authentication 

- The main approach to authentication is AuthenticationManager interface which has only one method :
    - public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}

- This method can achieve 3 Type of authentication :
    - Returns authentication usually authenticated = true.
    - Throws AuthenticationException if principal is not authenticated.
    - returns null if neither can be decided.

- Another method is used called Authentication provider :
The same as authentication manager but have one extra method support(class that extends authentication).
- Has one parent providermanager which will consult if It couldn't decide and throws an exception otherwise.
- Spring security provides some configuration helpers to configure some security settings to be set up in the application.

## Authorization or Access Control

- After authentication is done successfully authorization can be done after that.
- The main strategy used in the framework is AccessDecisionManager.
- ConfigAttribute is the interface used to handle authorization methods.
- Has one method that have the accessed roles.

### Web Security

- Spring web security is based on servlet filters.
- The proccess can be illustrated in chaining a number of ordered filters that is applied to a request until it reaches a client or server.
- FiltersChainProxy is the first filter implemented with spring security.
- The security filters are @Bean's in the ApplicationContext.
- FilterChainProxy is the parent of all implemented filters.
- By extending configure method from WebSecurityConfigurerAdapeter and the class that holds it can be annotated with the Order annotation to give a priority to each secured class.
- Request matchers are configurations used to apply security to a specific HTTP requests.
- Securing a method is that the user have to go through security authentications to execute the method useing the secured annotations.

## Spring Auth Cheat Sheet

- Set up model and repo.
- create a controller for that model.
- implementation of usersdetails service implements user details.
- Application User implements user details override the neccesary methods and make them return true.
- Configure web security config class it should :
    - has user detail service.
    - password encoder autowired.
    - configure authmanagerbuilder.
    - Configure http security by overriding the configure method.
    - Form login .
    - Add matchers.
    - logout functionality.

- Add Login page form.
- Add signup page.
- validate the controllers of both.