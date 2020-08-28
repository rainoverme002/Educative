# Different tier in software architecture

## Proof of Concept

- helps us get a closer, more hands-on view of the technology & the basic use case implementation
- It helps with the learning curve if we’re working with completely new tech, also the non-technical people like the product owners, stakeholders 

## What is it?

- a tier as a logical separation of components in an application or a service

Components

- Database
- Backend application server
- User interface
- Messaging
- Caching

### Single Tier Applications

- an application where the user interface, backend business logic & the database all reside in the same machine

pros:

- no network latency
- the data of the user stays in his machine & doesn’t need to be transmitted over a network

cons:

- vulnerable to being tweaked & reversed engineered
- no code or features changes can possibly be done until the customer manually updates it

### Two Tier Applications

- involves a client and a server
- The client would contain the user interface & the business logic in one machine. And the backend server would be the database running on a different machine.

pros:

- no network latency
- the data of the user stays in his machine & doesn’t need to be transmitted over a network

cons:

- vulnerable to being tweaked & reversed engineered
- no code or features changes can possibly be done until the customer manually updates it

### Three Tier Applications

- pretty popular & largely used in the industry. Almost all of the simple websites like blogs, news websites etc. are part of this category
- the user interface, application logic & the database all lie on different machines & thus have different tiers. They are physically separated.

### N-Tier Application

- An N-tier application is an application which has more than three components involved.

#### Why The Need For So Many Tiers? 

- Single Responsibility Principle, simply means giving one, just one responsibility to a component & letting it execute it with perfection.
- Separation of concerns, kind of means the same thing, be concerned about your work only & stop worrying about the rest of the stuff.
