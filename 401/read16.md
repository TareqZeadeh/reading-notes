# Spring Boot and OAuth2
- There are several samples building on each other, adding new features at each step:

    * simple: a very basic static app with just a home page and unconditional login via Spring Boot’s OAuth 2.0 configuration properties (if you visit the home page, you will be automatically redirected to GitHub).

    * click: adds an explicit link that the user has to click to login.

    * logout: adds a logout link as well for authenticated users.

    * two-providers: adds a second login provider so the user can choose on the home page which one to use.

    * custom-error: adds an error message for unauthenticated users, and a custom authentication based on GitHub’s API.



- Creating a New Project : 

   * you need to create a Spring Boot application, which can be done in a number of ways. The easiest is to go to https://start.spring.io and generate an empty project (choosing the "Web" dependency as a starting point). Equivalently, do this on the command line:

   ```
   $ mkdir ui && cd ui
   $ curl https://start.spring.io/starter.tgz -d style=web -d name=simple | tar -xzvf -
   ```

- Add a Home Page : 

   * create index.html in the src/main/resources/static folder.

- Securing the Application with GitHub and Spring Security : 

   * To make the application secure, you can simply add Spring Security as a dependency.


   ```
   <dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-oauth2-client</artifactId>
   </dependency>
   ```

- Add a New GitHub App : 

   * Select "New OAuth App" and then the "Register a new OAuth application" page is presented. Enter an app name and description. Then, enter your app’s home page, which should be http://localhost:8080, in this case. Finally, indicate the Authorization callback URL as http://localhost:8080/login/oauth2/code/github and click Register Application.

- Configure `application.yml`

   ```
   spring:
  security:
    oauth2:
      client:
        registration:
          github:
            clientId: github-client-id
            clientSecret: github-client-secret
   ```