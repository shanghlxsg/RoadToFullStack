# API design patterns and best practices

* Detailed designs aim to achieve the following:
  * Define consistent practices and patterns for all API endpoints.
  * Adhere as closely as possible to accepted HTTP/REST best practices in the developer community at-large.
  * Make accessing services via REST interfaces easy and intuitive for all application developers and API consumers.
  * Allow service developers to leverage and reuse prior work on other services to implement, test and document consistently defined RESTful endpoints.
  * Enable partners (e.g. non-developers, third parties) to use these guidelines as a playbook for building API-consuming applications and integrations.

## Design princples

* If we are ever in doubt on an API design or implementation choice, may these Design Principles help guide us to the correct decision.

  1. Build for the consumer.
        APIs do not exist for their own sake, and are almost never the entry point for end users. Be mindful of which applications will be consuming our services, and go out of your way to cater to their requirements.

  2. Convention over configuration.
        Our APIs should be intuitive, and should adhere to and implement community standards wherever possible. Problem-solving is at the core of development, and is also the great expense. Avoid implementing custom solutions to problems others have already solved, and in doing so we'll avoid creating new problems of our own design for API consumers and code base maintainers.

  3. Optimize close to the metal.
        From authorization and serialization to filtering and sorting, we will gain greater efficiencies the closer we are to the database. Keep this in mind when building multi-layer and service-dependent APIs.

## Resource naming

* In REST, the primary data representation is called [resource](https://restfulapi.net/resource-naming/). Having a consistent and robust REST resource naming strategy will prove one of the best design decisions in the long term.

### Singleton and collection resources

* A resource can be a singletone or a collection.
  * A collection resource `customers` can be identified using URI `/customers`.
  * A singleton resource `customer` can be identified using URI `/customers/{customerId}`.

### Collection and sub-collection resources

* A resource may contain sub-collection resources.
  * A sub-collection resource `accounts` of a particular singleton resource `customer` can be identified using URI `/customers/{customerId}/accounts`.
  * A singleton resource `account` inside the sub-collection resource `accounts` can be identified using URI `/customers/{customerId}/accounts/{accountId}`.

### URI

* RESTful APIs use URIs (Uniform Resource Identifies) to address resources. When resources are well named, an API is intuitive and easy to use. If done poorly, the same API can be challenging to use and understand.

### Best practices

* Use nouns to represent resources. RESTful URI should refer to a resource that is a thing (noun) instead of referring to an action (verb) because nouns have properties that verbs do not have similarly, resources have attributes.
  * Use a singular noun to denote `document` resource archetype (a singular concept that is akin to an object instance or database record).
  * Use a plural noun to denote `collection` resource archetype (a server-managed directory of resources).
  * Use a plural noun to denote `store` resource archetype (client-managed resource repository).
  * User a verb to denote `controller` archetype (executable functions, with parameters and return values, inputs, and outputs).

* Consistency is key. Use consistent resource naming conventions and URI formatting for minimum ambiguity and maximum readability and maintainability.
  * Lowercase letters should be preferred in URI paths.
  * Use forward slash `/` to indicate hierarchical relationships.
  * Do NOT use trailing forward flash `/` as a last character within a URI's path as it adds no semantic value and may be confusing.
  * Use hyphens `-` to improve readability of URIs.
  * Do not use underscore `_` as certain application fonts may partially or completely obscure the underscore character in some browsers.

* Do not use file extensions (e.g.,`.pdf`, `.xml`, etc.) as it does not add any advantage and unnecessarily increases the length of the URIs.
  * To highligh the media type of API using file extension, rely on the media type communicated through the `Content-Type` header to determine how to process the body's content.

* Do not use URIs to indicate a CRUD function. URIs should only be used to uniquely identify the resources and not any action upon them. Use HTTP request methods instead to indicate which CRUD function is performed.
  * Refresher: CRUD = `CREATE`, `READ`, `UPDATE`, `DELETE`.

* Use query component to filter URI collection. Instead of creating new APIs, enable sorting, filtering, and pagination capabilities in resource collection API and pass the input parameters as query parameters.

## HTTP Verbs/Methods

* HTTP methods, also known as HTTP verbs, have semantic meaning (similar to how resources are equivalent to nouns).

### GET

* `GET` requests are used to retrieve data from a server at the specified resource.
  * Defined as part of the JSON API Specification.
  * Request is successful if it returns a `200` status code.
  * Ensure that a `GET` request to a specific resource returns the correct data.

### POST

* `POST` requests are used to send data to the API server to create or update a resource. The data sent to the server is stored in the request body of the HTTP request.
  * Defined as part of the JSON API Specification.
  * `POST` requests are non-idempotent. It mutates data on the backend server (as opposed to a `GET` request which does not change any data).
  * Request is successful if it returns a `200` status code.
  * Check that the data was saved correctly using `GET`.
  * Add tests that ensure `POST` requests fail with incorret or ill-formatted data.

### PUT

* `PUT` requests are used to send data to the API as a complete replacement of content.
  * `PUT` requests are idempotent.
  * Calling the same `PUT` request multiple times will always produce the same result.
  * In contrast, calling a `POST` request repeatedly will have the side effects of creating the same resource multiple times.
  * Request is successful if it returns a `201 (Created)`, `200 (OK)`, or `204 (No Content)` status code.
  * `PUT` requests should fail if invalid data is supplied in the request.

### PATCH

* `PATCH` requests are one of the lesser-known HTTP methods that only apply partial modifications to the resource (see IETF RFC 5789).
  * `PATCH` requests are non-idempotent. It does not need the full data unlike `POST` and `PUT` requests.
  * Check that a valid `PATCH` request returns a `2xx` status code.
  * `PATCH` requests should fail if invalid data is supplied in the request.

### DELETE

* `DELETE` requests are used to the resource at the specified URI.
  * Defined as part of the JSON API Specification.
  * Non-idempotent, should be heavily tested as it removed data from a database.
  * Request is successful if the subsequent `GET` request returns a `404 (Not Found)` status code.
  * Calling a `DELETE` request to an unknown resource should return a non-`200` status code.

### HEAD

* `HEAD` requests are almost identical to `GET` requests except without the response body.
  * `HEAD` requests are useful for checking what a `GET` request will return before actually making a `GET` request.
  * `HEAD` requests are also useful for API smoke testing by making a `HEAD` request against every API endpoint to ensure they are available.
  * Note that not every endpoint that supports `GET` will support `HEAD`, depending on the API.
  * When testing an API with `HEAD` requests:
    * Verify and check HTTP headers returned from a `HEAD` request.
    * Test requests with various query parameters to ensure that the API responds.

### OPTIONS

* `OPTIONS` requests should return data describing what other methods and operations the server supports at the given URL. If an API isn't expecting an OPTIONS request, it is good to put a test case in place that verifies failing behaviour.
  * Testing an `OPTIONS` request is dependent on the web service - whether or not it supports that and what it is supposed to return will define how you should test it.
  * Test endpoints that do not support `OPTIONS` and ensure that they fail properly.

## HTTP Response Codes

### `1xx` information response

* `100 Continue`
