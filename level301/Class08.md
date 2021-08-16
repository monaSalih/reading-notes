* What does REST stand for?
✔ Representational State Transfer as an architectural approach to designing web services.

* REST APIs are designed around a __resources__.

* What is an identifer of a resource? Give an example.
✔ is a URI that uniquely identifies that resource.
 ✔ exampl 
 ```
 https://adventure-works.com/orders/1
 ```

* What are the most common HTTP verbs?
✔ GET ✔ PATCH  ✔DELETE.
✔ POST ✔ PUT

* What should the URIs be based on?
✔ nouns (the resource) and not verbs (the operations on the resource) 

* Give an example of a good URI.
```
https://adventure-works.com/orders // Good
```
* What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?
✔ expose a large number of small resources 
Bad, chatty API, as defined by Reese, is any API that requires consumer to do more than a single call to perform a single, common operation. 

* What status code does a successful GET request return?
✔ 201 (Created)
*  What status code does an unsuccessful GET request return?
✔ 404 (Not Found).
*  What status code does a successful POST request return?
✔ 201 (Created).
*  What status code does a successful DELETE request return?
✔ 204 (No Content)