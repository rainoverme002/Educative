# Web Architecture

- involves multiple components like database, message queue, cache, user interface & all running in conjunction with each other to form an online service.

## Client Server Architecture

- works on a request-response model
- client sends the request to the server for information & the server responds with it.

### Client Side

- Desktop, Mobile, Web UI
- ReactJS, AngularJS, VueJS, Jquery

### Types of Client

- Thin Client is the client which holds just the user interface of the application, no business logic of any sort. (3 Tier App or more)
- thick client holds all or some part of the business logic (2 Tier App)

## Webserver

- a web server is to receive the requests from the client & provide the response after executing the business logic based on the request parameters received from the client
- In modern application development, even the user interface is hosted separately on a dedicated server
- We can use server-side rendering for the home page & for the other static content on our website & use client-side rendering for the dynamic pages.

There are a specific task server:

- Proxy server
- Mail server
- File server
- Virtual server

### Client Side Render

- works best for modern dynamic Ajax-based websites

### Server-Side Rendering

- Server render the HTML, CSS, and JS UI
- faster rendering of the UI, averting the UI loading time in the browser window
- perfect for delivering static content, such as WordPress blogs
- good for SEO as the crawlers can easily read the generated content

### REST API

- Representational State Transfer
- communication between the client and the server is a stateless process (no information or memory carried over from the previous communications)
- REST is used to decouple the front end and back end

### API Gateway

- a single entry point into the system
- Handles all the client requests, taking care of the authorization, authentication, sanitizing the input data & other necessary tasks before providing access to the application resources

## HTTP push and pull

### HTTP push

- HTTP Pull, The client pulls the data from the server whenever it requires
- (not ideal & a waste of resources if there is no more new data)
- AJAX (using interval to pull data)
  
### HTTP pull

- HTTP Push, The client sends the request for particular information to the server, just for the first time, & after that the server keeps pushing the new updates to the client whenever they are available
- (usually called as Callback, and can save a lot of network bandwidth & cut down the load on the server)

Example

- AJAX Long polling (like AJAX, but server holds the response until it finds an update)
- Web Sockets (a persistent bi-directional low latency), example : messaging, chat applications, real-time social streams & browser-based massive multiplayer games
- HTML5 Event Source (automatically pushes the data to the client whenever the updates are available, and data flow is in one direction only)
- Message Queues
- Streaming over HTTP (we need to stream large data over HTTP by breaking it into smaller chunks)
