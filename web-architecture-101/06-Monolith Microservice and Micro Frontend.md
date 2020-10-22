# Monolith, Microservice, and Micro Frontends

## Monolith

- simple to build, test & deploy
- self-contained, single-tiered software application

- What is the most suitable cases?
  - requirements are pretty simple,
  - the app is expected to handle a limited amount of traffic

- Pros of Monolith:
  - simplicity

- Cons of Monolith:
  - Continuous deployment (need to redeploy whole app if there is a minor changes)
  - Prone to regression
  - Single Points Of Failure
  - Not Flexible and Scalable
  - Cannot Leverage Heterogeneous Technologies

## Microservice

- Use "Single Responsibility & the Separation of Concerns" concept
- Different features/tasks are split into separate respective modules/codebases

- What is the most suitable cases?
  - complex use cases and for apps which expect traffic to increase exponentially in future

- Pros of Microservice:
  - No Single Points Of Failure
  - Leverage the Heterogeneous Technologies
  - Independent & Continuous Deployments

- Cons of Microservice:
  - Complexities In Management
  - No Strong Consistency

## The Trade offs between Monolith and Microservice

- Microservice: it’s easy for us to isolate faults and debug them
- Microservice: has a development Team Autonomy and increase productivity and the velocity of the teams.
- Monolith: Reduce complexity
- Nice story: [Segments from Monolith to Microservice and go back again](https://segment.com/blog/goodbye-microservices/)

## Micro Frontends

- loosely coupled components of the user interface
- provide fault isolation
- provide freedom of technology
- Easier Co-ordination With The Front End Devs

- Client side integration
  - Page link between modules
  - Iframe
  - Single SPA framework

- Server side integration
  - cuts down the loading time of the website
  - Some of the frameworks:
    - [Open Components](https://opencomponents.github.io/)
    - [Project Mosaic](https://www.mosaic9.org/)
    - [Podium](https://podium-lib.io/)
