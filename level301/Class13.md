# Which HTTP Status Code to Use for Every CRUD App

**100’s=**

✔ These are informational status codes; they usually tell the client that the header part of the request has been received and the server will try to comply with a transmission demand of the client.

**200’s=** 

✔ They tell the client that its request was accepted.

**300’s=** 

✔ They tell the client that the resource they are requesting isn’t available at the expected location anymore. 

**400’s=** 

✔  They are all about invalid requests a client sent to a server.

**500’s=**  
Often they indicate problems with overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server. 

* What is a status code 202?
✔ this doesn’t mean the request was successfully processed only that it met all validation requirements at the time of sending.


* What is a status code 308?
✔ This tells the client to use another URL to access the resource and not use the current URL anymore 

* What code would you use if an update didn’t  return data to a client?

✔ 204 No Content,for example when just saving a currently edited document. 

* What code would you use if a resource used to exist but no longer does?

✔ 410 Gone

* What is the ‘Forbidden’ status code?

✔ 403 Forbidden - The client has authorized or doesn’t need to authorize itself, but still has no permissions to access the resource 


# Mongo-DB



* What is middleware?

Middleware is software that provides common services and capabilities to applications outside of what’s offered by the operating system. 

* What does app.use(express.json()) do?

 is a method inbuilt in express to recognize the incoming Request Object as a JSON Object. 

* What does the /:id mean in a route?

pass a parameter

* What is the difference beween PUT and PATCH?

The main difference between the PUT and PATCH method is that the PUT method uses the request URI to supply a modified version of the requested resource which replaces the original version of the resource, whereas the PATCH method supplies a set of instructions to modify the resource.


* How do you make a defalut value in a schema?

```
category: {
    type: String,
    default: ''
}
```

* What does a 500 error status code mean?

server error response code indicates that the server encountered an unexpected condition that prevented it from fulfilling the request.

* What is the difference between a status 200 and a status 201?

200: It means, simply, that the request was received and understood and is being processed
201:status code indicates that a request was successful and as a result, a resource has been created (for example a new page).