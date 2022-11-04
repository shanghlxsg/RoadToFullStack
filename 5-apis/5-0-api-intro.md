# Introduction to APIs

[Source](https://www.moesif.com/blog/api-guide/getting-started-with-apis/).

## What is an API?

* API = Application Programming Interface.

* APIs is how machines talk to each other to create complex applications (apps).

* APIs can refer to an interface to a local library or the libraries themselves, and over the network to connect clients and servers (or multiple servers).

* APIs can be:
  * Local or web-based.
  * Internal or third party (to avoid reinventing the wheel).

## Good APIs

* Easy to learn.
* Easy to use.
* Hard to misuse.
* Easy to read and maintain code that uses it.
* Easy to extend.
* Appropriate to the audience.

## Core Principles of RESTful API

* (Re)presentational (S)tate (T)ransfer.

### Client-Server Architecture

* [Separation of concerns](../1_CS50x/1_introduction-to-software-engineering.md#separation-of-concerns).

### Statelessness

* The statelessness refers to that the server do not store any client context between each request. It is a design principle that is applied within the service-orientation design paradigm, in order to design scalable services by separating them from their state data whenever possible.

* REST is specifically designed to be functionally stateless, hinging on the idea of passing all data to handle the request in such a way as to pair the data within the request itself.

* Stateful applications and processes, however, are those that can be returned to again and again, like online banking or email (it can be wasteful and unnecessary to maintain a server state independent of the state of user).

* In terms of web services, the commonly accepted paradigm is to avoid sessions at all costs. Using sessions as a method for communicating state is generally something you want to avoid for the simple fact that sessions are not scalable.

### Cachability

* Following the stateless principle, if each request is stateless and have all the necessary information for the server to produce a result, then theoretically the results can be cached.

* Caching refers to storing the server response in the client itself, so that a client need not make a server request for the same resource again and again.

* Caching improves speed, fault tolerance, scalability, and reduces server load.

### Layered system

* This means that the client does not and should not need to know if it is directly connected to the server or some other layer, allowing for proxies and load balancers.

### Uniform interface

* Resource-based: individual resources are identified in requests using URIs as source identifiers.

* Manipulation of resources through representations: when a client holds a representation of a resource, including any metadata attached, it has enough information to modify or delete the resource on the server, provided it has permission to do so.

* Self-descriptive messages: each message includes enough information to describe how to process the message.

* Hypermedia as the engine of application state (HATEOAS): a hypermedia-driver site provides information to nagivate the site's REST interfaces dynamically by including hypermedia links with the responses.
