# Types of API (Comparison of API architectural styles)

* RESTful APIs using JSON on the HTTP protocol is by far the most popular approach to creating web APIs.

* The three key aspects for these different types:
  * Design Philosophy/Pattern (e.g. RESTful vs GraphQL)
  * Communication Protocol (e.g. HTTP vs WebSockets)
  * Encoding (e.g. Human readable text such as JSON vs Binary formats like ProtoBuf)

## GraphQL

* [GraphQL is a query language](https://graphql.org/learn/) for your API, and a server-side runtime for executing queries using a type system you define for your data.

* [GraphQL is a syntax](https://www.freecodecamp.org/news/so-whats-this-graphql-thing-i-keep-hearing-about-baf4d36c20cf)  that describes how to ask for data, and is generally used to load data from a server to a client.

* GraphQL has three main characteristics:
  * It lets the client specify exactly what data it needs.
  * It makes it easier to aggregate data from multiple sources.
  * It uses a type system to describe data.

* GraphQL and REST can work together as well. Choose the right tools for your application.
  * If your application’s data model have a lot of complex entities that reference each other (like Facebook), GraphQL make sense.
  * If you have only few data entities, and the additional complexity of implementing GraphQL may not worth it.

## RPC

* Remote Procedure Call (RPC) is one of the oldest programming client-server protocols for APIs. It is still used to this day, although it has taken on many different forms.

* RPC provides a different paradigm for accessing network services. Instead of accessing remote services by sending and receiving messages, a client invokes services by making a local procedure call while the details of the network communication.

* RPC-based APIs are better for procedure or commands, while REST is more about modeling the data and state.

## WebSockets vs HTTP

* The [WebSocket specification](https://web.dev/websockets-basics/) defines an API establishing "socket" connections between a web browser and a server. In plain words: There is an persistent connection between the client and the server and both parties can start sending data at any time.

* [HTTP](https://medium.com/platform-engineer/web-api-design-35df8167460) is the underlying communication protocol of the World Wide Web. HTTP functions as a request-response protocol in the client-server computing model. In general, RESTful APIs uses HTTP as its transport protocol.

## JSON vs XML

* For RESTful APIs, the format used for transfer data is almost always JSON. But JSON isn’t the only way to encode data. XML can be used also. Even if we default to JSON, it may worth a while to understand the differences.

### XML

* XML stands for eXtensible Markup Language and is a markup language much like HTML. XML was designed to be self-descriptive and to store and transport data (XML does not DO anything per se).

* Compared to HTML that was designed to display data, XML was designed to carry data, and XML tags are not predefined like HTML tags are.

### JSON

* [JSON (JavaScript Object Notation)](https://www.json.org/json-en.html) is a lightweight data-interchange format, easy for humans to read and write, easy for machines to parse and generate.

* JSON is built on two structures:
  * A collection of name/value pairs. In various languages, this is realized as an object, record, struct, dictionary, hash table, keyed list, or associative array.
  * An ordered list of values. In most languages, this is realized as an array, vector, list, or sequence.

## Binary protocols

### ProtoBuf (Protocol Buffers)

* [Protocol Buffers](https://developers.google.com/protocol-buffers/) are Google’s language-neutral, platform-neutral, extensible mechanism for serializing structured data – think XML, but smaller, faster, and simpler.

### Thrift

* [Thrift](https://thrift.apache.org/) is created by Apache. They provide a code generation engine that create stubs for pretty much all languages.

### MessagePack

* The tagline for [MessagePack](https://msgpack.org/index.html) is “It’s like JSON, but fast and small.” MessagePack is an efficient binary serialization format.

## Legacy technologies

### SOAP

* Basically the [precursor to REST](https://www.upwork.com/hiring/development/soap-vs-rest-comparing-two-apis/).

### COBRA

* Common object request broker architecture (COBRA) is a discontinued general-purpose, object-oriented programming language designed as an improvement to RPC.
