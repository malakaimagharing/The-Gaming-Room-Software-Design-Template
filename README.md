# The-Gaming-Room-Software-Design-Template
1. Client and Software Requirements
The Gaming Room (TGR) is a start-up that operates an online party game called Draw It or Lose It. Initially released only as an Android app, TGR asked Creative Technology Solutions (CTS) to design a web-based, multi-platform version that could:

host one active game service in memory at a time (Singleton)

support multiple teams, each with multiple players

guarantee unique names and IDs for games, teams, and players

follow clean object-oriented principles so the code can be ported easily to Linux, Windows, macOS, and mobile browsers in a distributed environment.

2. What Went Well
I clearly separated business requirements (what TGR needs) from technical requirements (how we will build it). Creating the Entity base class and the GameService Singleton early kept the UML, Java code, and documentation aligned, which reduced re-work.

3. How the Design Document Helped the Code
Working through each section of the design template—especially the Domain Model and Design Constraints—forced me to think about inheritance, ID generation, and name-uniqueness before I started coding. That up-front clarity meant the Java classes fit together with minimal refactoring.

4. If I Could Revise One Part
I would revisit the System Architecture View and expand it with a diagram showing future micro-services and a load balancer. Adding those details would make the document more useful when the team scales the game to thousands of concurrent users.

5. Interpreting and Implementing User Needs
The client’s top priority was unique game/team/player names so users never collide while picking names. I implemented an iterator-based check in each addGame, addTeam, and addPlayer method plus centralized ID counters in GameService. Considering user needs early prevents UX friction and costly redesigns later.

6. My Design Approach and Future Techniques
I used a “design-then-code” loop:

Capture high-level user stories.

Sketch UML classes (Entity → Game/Team/Player).

Map each class to a design-pattern responsibility (Singleton, Iterator).

Code small vertical slices and test with a driver script.

In future projects I will add:

Event-storming to surface domain events quickly.

T-Shirt sizing or Planning-Poker estimates before coding.

Automated unit tests from day one to lock down class behaviors.
