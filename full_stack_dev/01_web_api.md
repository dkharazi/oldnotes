## General Introduction
- Servers communicate with each other by sending each other packet requests and responses
- These requests and responses follow a network-layer protocol, such as IP or TCP
- In other words, servers will send each other either IP-formatted packets or TCP-formatted packets across a network
- Within those IP packets, there is a data chunk
- These data chunks follow an application-layer protocol, such as SOAP, HTTP, HTTPS, FTP, SMTP, etc.
- In other words, applications will send each other HTTP-formatted data chunks, SMTP-formatted data chunks, etc.

## Separation of the Front-end and Back-end
- Typically, the front-end and back-end live on separate web servers
- The front-end will send HTTP-formatted requests to the back-end
- The back-end will interpret those HTTP-formatted requests
- The back-end will send HTTP-formatted responses (containing the response code and JSON-formatted data) back to the front-end
- The front-end will interpret those HTTP-formatted responses, and extract the JSON-formatted data if their interaction was successful

## General Description of APIs
- In general terms, an API is a set of methods (for communication between other software components)
	- These methods can follow a protocol, such as HTTP, SMTP, etc.
- A web service (or web API) is a set of methods that understand HTTP-formatted requests
	- In other words, these methods specifically follow an HTTP protocol
	- Also, web services respond to the front-end client with an HTTP-formatted response code and XML-formatted or JSON-formatted data
- A web service is a form of an API
- In other words, all web services are APIs, but not all APIs are Web Services
- A web service always needs a network for its operation, whereas an API doesn't need a network for its operation
- An API deals with communication between software in general, whereas a web service deals with communication between software on two different machines over a network

## HTTP Methods
- HTTP methods represent the protocol between applications across the web
- In other words, the front-end and back-end communication with each other through HTTP
- CRUD operations represent the four very broad computer science functions:
	- Create
	- Read
	- Update
	- Delete
- HTTP protocol is a collection of the five general methods, which are very similar to the CRUD operations:
	- POST
	- GET
	- PUT
	- PATCH
	- DELETE

## References
- https://en.wikipedia.org/wiki/List_of_network_protocols_(OSI_model)
- http://www.differencebetween.net/technology/internet/difference-between-api-and-web-service/#ixzz3e3WxplAv
- https://stackoverflow.com/questions/18783397/should-frontend-or-backend-utilise-web-services
- https://www.youtube.com/watch?v=LooL6_chvN4
- https://stackoverflow.com/questions/19336347/what-is-the-difference-between-a-web-api-and-a-web-service
- https://en.wikipedia.org/wiki/Create,_read,_update_and_delete
