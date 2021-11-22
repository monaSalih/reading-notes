# JSON

## What is JSON Web Token?

that defines a compact and self-contained way for securely transmitting information between parties as a JSON object. 

## When should you use JSON Web Tokens?
Here are some scenarios where JSON Web Tokens are useful:
* Authorization: This is the most common scenario for using JWT. Once the user is logged in, each subsequent request will include the JWT, allowing the user to access routes, services, and resources that are permitted with that token.
* Information Exchange: JSON Web Tokens are a good way of securely transmitting information between parties. Because JWTs can be signed—for example, using public/private key pairs—you can be sure the senders are who they say they are

## What is the JSON Web Token structure?
In its compact form, JSON Web Tokens consist of three parts separated by dots (.), which are:
* Header:
The header typically consists of two parts: the type of the token, which is JWT, and the signing algorithm being used. 
* Payload:
which contains the claims. Claims are statements about an entity (typically, the user) and additional data.
- There are three types of claims:
* Registered claims: These are a set of predefined claims which are not mandatory but recommended, to provide a set of useful, interoperable claims.
* Public claims: These can be defined at will by those using JWTs. 
Private claims: These are the custom claims created to share information between parties that agree on using them and are neither registered or public claims.
* Signature:
To create the signature part you have to take the encoded header, the encoded payload, a secret, the algorithm specified in the header, and sign that.

## How do JSON Web Tokens work?
In authentication, when the user successfully logs in using their credentials, a JSON Web Token will be returned.
The following diagram shows how a JWT is obtained and used to access APIs or resources:
![](https://cdn2.auth0.com/docs/media/articles/api-auth/client-credentials-grant.png)

## Why should we use JSON Web Tokens?

As JSON is less verbose than XML, when it is encoded its size is also smaller, making JWT more compact than SAML. This makes JWT a good choice to be passed in HTML and HTTP environments.

## How JWT Works?
The JWT is just an authorization token that should be included in all requests:
```
curl http://127.0.0.1:8000/hello/ -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQzODI4NDMxLCJqdGkiOiI3ZjU5OTdiNzE1MGQ0NjU3OWRjMmI0OTE2NzA5N2U3YiIsInVzZXJfaWQiOjF9.Ju70kdcaHKn1Qaz8H42zrOYk0Jx9kIckTn9Xx7vhikY'
```
* The access token is usually short-lived (expires in 5 min or so, can be customized though).
* The refresh token lives a little bit longer (expires in 24 hours, also customizable). 

- Why is that?
you will see the token is composed by three parts:
```
xxxxx.yyyyy.zzzzz
```
Those are three distinctive parts that compose a JWT:
```
header.payload.signature
```
So we have here:
```
header = eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9
payload = eyJ0b2tlbl90eXBlIjoiYWNjZXNzIiwiZXhwIjoxNTQzODI4NDMxLCJqdGkiOiI3ZjU5OTdiNzE1MGQ0NjU3OWRjMmI0OTE2NzA5N2U3YiIsInVzZXJfaWQiOjF9
signature = Ju70kdcaHKn1Qaz8H42zrOYk0Jx9kIckTn9Xx7vhikY
```

## Django Runserver Is Not Your Production Server

You’ve built your Django web app and are working on deploying it.You’ve been running your app locally with python manage.py runserver. That’s a fine command, built for development convenience, but it’s not meant to be used as part of a production setup

## A Production Stack
You want to only use tech in production, which is reliable, well tested and has been around for a while.

## How Does Django Fit In?
Your Django app does not actually run as you would think a server would - waiting for requests and reacting to them. Your project provides a uwsgi.py file, which contains a function to be called by the application server. 

### In Conclusion
If you want to run Django in production, be sure to use a production-ready web server like Nginx, and let your app be handled by a WSGI application server like Gunicorn.