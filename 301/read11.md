# What is OAuth? How the open authorization framework works.
## 1.What is OAuth?
#### OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential.
## 2.Give an example of what using OAuth would look like.
#### The simplest example of OAuth is when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you, and the website you were originally connecting to logs you on itself afterward using permission gained from the second website.(Like the way we used to sign-up on netlify using our GitHub account.)
## 3.How does OAuth work? What are the steps that it takes to authenticate the user?
#### Let’s assume a user has already signed into one website or service (OAuth only works using HTTPS). The user then initiates a feature/transaction that needs to access another unrelated site or service. The following happens (greatly simplified):
1.The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.
2.The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.
3.The first site gives this token and secret to the initiating user’s client software.
4.The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).
5.If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.
6.The user approves (or their software silently approves) a particular transaction type at the first website.
7.The user is given an approved access token (notice it’s no longer a request token).
8.The user gives the approved access token to the first website.
9.The first website gives the access token to the second website as proof of authentication on behalf of the user.
10.The second website lets the first website access their site on behalf of the user.
11.The user sees a successfully completed transaction occurring.
12.OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).
## 4.What is OpenID?
#### While the _auth_ in **OAuth** stood for _authorization_, not _authentication_, **OpenID** is about _authentication_: as a commenter on StackOverflow pithily put it: "OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans."

## =====================================
# Authentication and Authorization Flows.
## 1.What is the difference between authorization and authentication?
#### **Authentication** confirms that users are who they say they are. **Authorization** gives those users permission to access a resource.
##### Authentication is the act of validating that users are whom they claim to be. This is the first step in any security process.
##### Authorization in system security is the process of giving the user permission to access a specific resource or function. This term is often used interchangeably with access control or client privilege.
## 2.What is Authorization Code Flow
#### Because regular web apps are server-side apps where the source code is not publicly exposed, they can use the Authorization Code Flow, **which exchanges an Authorization Code for a token**.
## 3.What is Authorization Code Flow with Proof Key for Code Exchange (PKCE)?
#### During authentication, mobile and native applications can use the Authorization Code Flow, but they require additional security. Additionally, single-page apps have special challenges. To mitigate these, OAuth 2.0 provides a version of the Authorization Code Flow which makes use of a Proof Key for Code Exchange (PKCE).
##### **Simply**, **(PKCE)** is an extension to the Authorization Code flow to prevent several attacks and to be able to securely perform the OAuth exchange from public clients. It was originally designed to protect mobile apps, but its ability to prevent authorization code injection makes it useful for every OAuth client, even web apps that use a client secret.
## 4.What is Implicit Flow with Form Post?
#### As an alternative to the Authorization Code Flow, OAuth 2.0 provides the Implicit Flow, which is intended for Public Clients, or applications which are unable to securely store Client Secrets.
####  While this is no longer considered a best practice for requesting Access Tokens, when used with Form Post response mode, it does offer a streamlined workflow if the application needs only an ID token to perform user authentication.
## 5.What is Client Credentials Flow?
#### With machine-to-machine (M2M) applications, such as CLIs, daemons, or services running on your back-end, the system authenticates and authorizes the app rather than a user. For this scenario, typical authentication schemes like username + password or social logins don't make sense. Instead, M2M apps use the Client Credentials Flow .
##### **Simply**, The Client Credentials flow is a server to server flow. There is no user authentication involved in the process. In fact there is no user at all, the resulting access tokens will not contain a user, but will instead contain the Client ID as subject (if not configured otherwise). This flow is useful for systems that need to perform API operations when no user is present. It can be nightly operations, or other that involve contacting OAuth protected APIs.
## 6.What is Device Authorization Flow?
#### With input-constrained devices that connect to the internet, rather than authenticate the user directly, the device asks the user to go to a link on their computer or smartphone and authorize the device. This avoids a poor user experience for devices that do not have an easy way to enter text. To do this, device apps use the Device Authorization Flow (drafted in OAuth 2.0). For use with mobile/native applications.
#### **Simply**, The Device Flow, handles the scenario where user authentication is difficult to enter on the device itself. In a Device Flow, the flow is initiated by the device, but authentication is handled out-of-band on a different device with a better input, such as a browser with a keyboard for input. The initial device polls the authorization server for a completed and successful user authentication. When it’s available, tokens are issued. The Device Flow is a useful authorization flow commonly used with smart TVs and devices like Apple TV.
## 7.What is Resource Owner Password Flow?
#### Though we do not recommend it, highly-trusted applications can use the Resource Owner Password Flow, which requests that users provide credentials (username and password), typically using an interactive form. The Resource Owner Password Flow should only be used when redirect-based flows (like the Authorization Code Flow) cannot be used.
