# CS-230 Design Reflection (Draw It or Lose It)

## 1. Client & Requirements
The client, **The Gaming Room**, asked for a **web-based version** of their Android game *Draw It or Lose It*.  
Key needs: preserve core gameplay (four timed rounds, team guessing), support **cross-platform browser access**, maintain **one active game instance** per server process, enforce **unique IDs/names** for games/teams/players, and expose **RESTful APIs** for game, team, and player management under a scalable, secure architecture.

## 2. What I Did Well
Structured the domain cleanly using a common `Entity` base, a `GameService` singleton for lifecycle and ID management, and REST endpoints that map neatly to game actions—making the logic consistent and easy to extend.

## 3. Helpful in Code Development
The class/relationship definitions (Game → Team → Player) and API surface written up front reduced ambiguity, so implementation became filling in well-scoped services and controllers rather than re-deciding behavior mid-build.

## 4. Potential Revisions
I’d expand **non-functional details**: add concrete performance SLOs (e.g., render/timer latency targets), capacity assumptions, and load-test plans; also detail deployment topology (LBs, autoscaling rules) with diagrams to make scaling and failover expectations explicit.

## 5. Interpreting & Implementing User Needs
User pain points—simple join/play flows, reliable timers, no duplicate names, and smooth team coordination—were translated into server-validated uniqueness, in-memory caching for hot state, and clear REST/WebSocket boundaries.  
Prioritizing these needs ensures usability, prevents errors (like name collisions), and directly supports engagement and retention.

## 6. Design Approach & Future Strategy
Approach: start with domain modeling → define service boundaries and APIs → map non-functionals (security, latency, scalability) to concrete tech (Linux, RDBMS + cache, TLS, JWT/OAuth).  
In the future I’d add **C4 diagrams**, **ADR notes** for key choices, **sequence diagrams** for real-time rounds, and **threat modeling** to formalize security from the start.
