# CS 230 Portfolio — The Gaming Room

Michael Anderson\
Southern New Hampshire University | CS 230: Operating Platforms

## Project Artifact

Software Design Document: `CS_230_Project_Three_Completed.docx`

## Portfolio Reflection

### 1. Briefly summarize The Gaming Room client and their software requirements.

The Gaming Room was a client seeking to expand its existing Android game --- Draw It or Lose It into an application available across multiple operating platforms. In this team based drawing and guessing game players identify images rendered from a library of clues. The client needed a web accessible solution that supported multiple teams and players, unique game and team names, and only one active instance of the game service.

The new design also needed to be secure, scalable, and consistent across devices while also managing game sessions and shared data reliably.

### 2. What did you do particularly well in developing this documentation?

I believe I did particularly well at connecting the client's funtional requirements to specific technical design decisions. I compared operating platforms, identified tradeoffs involving cost, scalability, compatibility, and maintainability, and explained why a Linux-hosted Java application with centralized relational storage was a strong fit.

I also documented the role of the `GameService` singleton, unique identifiers, and checks for duplicate names so the proposed architecture remained connected to the game's actual behavior. I hit on making the recommendations understandable to both technical team members and the client.

### 3. What about the process of working through a design document did you find helpful when developing the code?

The design document helped translate a broad client request into smaller, testable responsibilities before implementation. Identifying the required classes, data relationships, and service boundaries made it easier to reason about what each component should do.

For example, the UML and object oriented design clarified how the singleton pattern would manage the game service and how iteration could be used to locate games or prevent duplicate names. Planning these decisions ahead of time reduced ambiguity and provided a reference for development and tsting.

### 4. If you could choose one part of your work on these documents to revise, what would you pick? How would you improve it?

I would expand the scalability and deployment section. Although the document recommends a centralized service architecture, I would add a deployment diagram and a clearer discussion of what could happen as the number of concurrent users increases.

I would also define measurable performance targets, describe how sessions and application state would work across multiple server instances, and compare load balancing and data caching options. These additions would make the recommendation easier to validate before production deployment.

### 5. How did you interpret the user's needs and implement them into your software design? Why is it so important to consider the user's needs when designing?

I began with what players and the client needed: access from different devices, dependable multiplayer sessions, unique game and team identities, fair timing, and protection of user and game data.

I mapped those needs to a responsive browser client, Java based application services, server controlled game logic, persistent database storage, and encrypted communication over HTTPS.

Considering user needs is essential because a technically sophisticated system can still fail if it is difficult to use as well as inconsistent across platforms, or unreliable during gameplay. The architecture should serve the experience people expect, not dictate an experience simply because a technology is available.

### 6. How did you approach designing software? What techniques or strategies would you use in the future to analyze and design a similar software application?

I approached the design by first examining the reuirements, then comparing platform architectures and selecting components that worked together as a complete system.

I used object oriented principles and design patterns to define game service behavior, evaluated operating system and storage considerations, and addressed security, networking, and distributed system concerns.

In future projects, I would continue to document requirements and alternatives early, use UML and architecture diagrams to communicate responsibilities, prototype high-risk components, and establish performance and security tests before deployment. I would also seek frequent client feedback so the design can evolve as requirements become clearer.

## Architecture Summary

| Component | Recommendation |
| --- | --- |
| Client | Responsive web interface for cross platform access |
| Application | Java game services and session management |
| Hosting | Linux based server |
| Database | PostgreSQL and image/object storage |
| Security | HTTPS and appropriate REST/WebSocket communication |
| Quality | Automated tests, validation, unique identifiers, scalability planning |
