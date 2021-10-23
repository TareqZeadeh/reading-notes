# Read: Class 19 Read: 19 - Spring and Sockets

## [Real time messaging with websockets](https://spring.io/guides/gs/messaging-stomp-websocket/)

1. STOMP is a subprotocol operating on top of the lower-level WebSocket.

### Using WebSocket to build an interactive web application

1. generate a new project with the required dependency (Websocket).
   - implementation 'org.webjars:webjars-locator-core'
   - implementation 'org.webjars:sockjs-client:1.0.2'
   - implementation 'org.webjars:stomp-websocket:2.3.3'
   - implementation 'org.webjars:bootstrap:3.3.7'
   - implementation 'org.webjars:jquery:3.1.1-1'
1. model the message that carries the name, create a plain old Java object with a name property and a corresponding getName()
1. model the greeting representation, add another plain old Java object with a content property and a corresponding getContent() method

### Create a Message-handling Controller

1. `The @MessageMapping` annotation ensures that, if a message is sent to the /hello destination, the `greeting()` method is called.
1. After the one-second delay, the `greeting()` method creates a Greeting object and returns it.
1. The return value is broadcast to all subscribers of `/topic/greetings`, as specified in the `@SendTo` annotation.

### Configure Spring for STOMP messaging

1. Create a Java class named `WebSocketConfig`

   - ```java
       @Configuration
       @EnableWebSocketMessageBroker
       public class WebSocketConfig implements WebSocketMessageBrokerConfigurer {
       @Override
       public void configureMessageBroker(MessageBrokerRegistry config) {
           config.enableSimpleBroker("/topic");
           config.setApplicationDestinationPrefixes("/app");
       }
       @Override
       public void registerStompEndpoints(StompEndpointRegistry registry) {
           registry.addEndpoint("/gs-guide-websocket").withSockJS();
       }
       }
     ```

1. `@Configuration` to indicate that it is a Spring configuration class.
1. `@EnableWebSocketMessageBroker` enables WebSocket message handling, backed by a message broker.
1. enableSimpleBroker() to:
   - enable a simple memory-based message broker to carry the greeting messages back to the client on destinations prefixed with `/topic`
   - designates the /app prefix for messages that are bound for methods annotated with `@MessageMapping`
1. The registerStompEndpoints() method registers the /gs-guide-websocket endpoint,
   - enabling SockJS fallback options so that alternate transports can be used if WebSocket is not available.
   - The SockJS client will attempt to connect to /gs-guide-websocket and use the best available transport (websocket, xhr-streaming, xhr-polling, and so on).

### Create a Browser Client

1. This HTML file imports the SockJS and STOMP javascript libraries that will be used to communicate with our server through STOMP over websocket.