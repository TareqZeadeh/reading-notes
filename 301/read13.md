# Status Codes Based On REST Methods
## 1. In your own words, describe what each group of status code represents:
### 100’s = 
#### These are informational status codes:  they usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.
### 200’s = 
#### These are the success codes:  They tell the client that its request was accepted. In case of asynchronous processing of a request (202), this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.
### 300’s =
#### These are redirection codes. They tell the client that the resource they are requesting isn’t available at the expected location anymore. 
### 400’s = 
#### These are the client error codes. They are all about invalid requests a client sent to a server. There are several causes to this, timeouts, wrong URI, missing authentication, etc.
### 500’s =
#### hese are the server error codes. Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. 
## 2.What is a status code 202?
#### **In CREATE** : Accepted - Often used for asynchronous processing. This code tells the client that the request was valid, but its processing will finish sometime in the future. The response body should include an URL to the finished resource with some information about when it will be available, or an URL to some monitoring endpoint that tells the client when the resource is available.

#### **In UPDATE** : Accepted - If the update is done asynchronous, this code can be used. It should include an URL to access the updated resource or an URL to check if the update has been succeeded. It can also include an estimation of how long the update will take.

## 3.What is a status code 308?
#### **In READ**: Permanent Redirect - This tells the client to use another URL to access the resource and not use the current URL anymore. It’s helpful when we have multiple endpoints for one resource, but don’t want to implement reading from all of them.
#### **In API Changes**:  Permanent Redirect - This is the right code if the resource will now be available at a new URL and the client should directly access it via the new URL in the future. The current endpoint can’t control the clients’ behavior after the request and a subsequent redirect if the resource URL changes again have to be issued from the new URL.
#### **In Multiple Endpoints for One ResourcePermalink** : Permanent Redirect - If we have nested resources _/user/kay/comments/456_ and _/posts/123/comments/456_; and a root resource _/comments/456_ it can make things easier to simply issue 308 redirects at the nested resources with the Location header field pointed to the root resource so not every endpoint needs a delivery implementation. This should only be done for GET requests.
#### **In Wrong URL**: Permanent Redirect - This would be the right code if we know that a resource has moved to a different URL and we can tell the client about it.

## 4.What code would you use if an update didn’t return data to a client?
#### **204 No Content**.
## 5.What code would you use if a resource used to exist but no longer does?
#### **410 Gone** .
## 6.What is the ‘Forbidden’ status code?
#### 403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource.