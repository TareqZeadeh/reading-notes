# Read: 09 - WRRC and Java

Here is a summary of what I learned from these articles:

## [Review: High-level HTTP](https://dev.to/dangolant/things-i-brushed-up-on-this-week-the-http-request-lifecycle-)

### The HTTP Request Lifecycle

##### Step 1: Local Processing

1. browser extracts the "scheme"/protocol (HTTP)
2. host (www.example.com) 
3. optional port number 8080
4. resource path
5. query strings

  `|http|://|www.example.com||:5000||/mainpage||?query=param&query2=param2|`

6. browser need to resolve an IP address by:
   1.  look through its own cache of recently requested URLs
   2.  the operating system’s cache of recent queries
   3.  your router’s cache
   4.  your DNS cache

#### Step 2: Resolve an IP

1. Like the processing done locally, resolving an IP from a "DNS server"2 is a sequence that includes many steps, and includes failovers if the first request fails to return an address.

2. Your request will now have to travel many network devices to reach its target DNS server.
3. Once your request arrives at your configured DNS server, the server looks for the address associated with the requested hostname. If it finds one, it sends a response. if the DNS server you have targeted cannot locate the given hostname, it passes the request along to another DNS server.If an address for the given domain cannot be resolved, the server responds with a failure and your browser returns an error.
4. the requesting client now has a target IP

#### Step 3: Establish a TCP Connection

The server must already be "listening" on a port, performing a passive open, after which the client can initiate an active open, and the handshake works as follows :

- TCP connections are opened using what’s known as a three-way handshake, the server must already be "listening" on a portable

#### Step 4: Send an HTTP Request

now that the client has an IP address and a TCP connection, it can finally send an HTTP request.

#### Step 5: Tearing Down and Cleaning Up

- now the response has been fully delivered
- At this point, your browser begins processing what it has received.
  
## [Java HTTP Request example](https://www.baeldung.com/java-http-request)

- The `HttpUrlConnection` class allows us to perform basic HTTP requests without the use of any additional libraries. (part of the java.net package)
- We can create an HttpUrlConnection instance using the `openConnection()` method of the URL class (create but doesn't establish the connection yet)
- The HttpUrlConnection class is used for all types of requests by setting the requestMethod attribute to one of the values: GET, POST, HEAD, OPTIONS, PUT, DELETE, TRACE.

```java
URL url = new URL("http://example.com");
HttpURLConnection con = (HttpURLConnection) url.openConnection();
con.setRequestMethod("GET");
```

- If we want to add parameters to a request, we have to set the doOutput property to true, then write a String of the form param1=value¶m2=value to the OutputStream
- Adding headers to a request can be achieved by using the `setRequestProperty()` method:
  `con.setRequestProperty("Content-Type", "application/json");`

- `HttpUrlConnection` class allows setting the connect and read timeouts. These values define the interval of time to wait for the connection to the server to be established or data to be available for reading

- To set the timeout values, we can use the setConnectTimeout() and setReadTimeout() methods:
  
```java
con.setConnectTimeout(5000);
con.setReadTimeout(5000);
```

- The java.net package contains classes that ease working with cookies such as `CookieManager` and `HttpCookie`.
- We can enable or disable automatically following redirects for a specific connection by using the `setInstanceFollowRedirects()` method with true or false parameter
- Reading the response of the request can be done by parsing the InputStream of the `HttpUrlConnection` instance
- To execute the request, we can use the `getResponseCode()`, `connect()`, `getInputStream()` or `getOutputStream()`

- if the request fails we can consume the stream provided by `HttpUrlConnection.getErrorStream()`.

- then we can build the Full Response.