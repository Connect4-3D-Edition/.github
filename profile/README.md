# Connect4-3D-Edition

Connect4-3D-Edition is the public home of a modular competitive strategy game platform built around a `4 x 4 x 4` Connect Four variant, with a dedicated frontend, split backend services, shared libraries, and supporting infrastructure.

## What lives here

This organization is split into focused repositories so each part of the stack can evolve independently while still forming one cohesive product:

| Repository | Purpose |
| --- | --- |
| [`.wrapper`](https://github.com/Connect4-3D-Edition/.wrapper) | Developer workspace with VS Code tasks, local setup, instructions, and coordinated checks |
| [`frontend`](https://github.com/Connect4-3D-Edition/frontend) | React-based client for the player experience and 3D presentation |
| [`service-api`](https://github.com/Connect4-3D-Edition/service-api) | FastAPI service for user-facing platform features such as authentication |
| [`game-api`](https://github.com/Connect4-3D-Edition/game-api) | FastAPI service for game-specific backend logic |
| [`common-lib`](https://github.com/Connect4-3D-Edition/common-lib) | Shared Python package used across backend repositories |
| [`db-migrations`](https://github.com/Connect4-3D-Edition/db-migrations) | Alembic-based database schema evolution and initial data population |
| [`infrastructure`](https://github.com/Connect4-3D-Edition/infrastructure) | Local database setup and infrastructure definitions |

The current application supports live multiplayer with FIFO queueing, ten-second match confirmation, ghost rivals after a twenty-second wait, WebSocket updates, five-minute clocks, and reconnectable matches, plus singleplayer training against the computer. Guests and members can play; persistent member profiles and histories include ghost accounts. Member-versus-member multiplayer uses Elo ratings, including ghosts; guest games and singleplayer are unrated.

## What the stack looks like

- The frontend is built with React and Babylon.js-related tooling for the client experience.
- Backend services are Python 3.12+ applications built around FastAPI and Uvicorn.
- Shared backend code is centralized in `common-lib`.
- Database changes are handled separately in `db-migrations`.
- Environment and deployment foundations live in `infrastructure`.
- Local developer onboarding and workspace entry live in `.wrapper`.

## Why it is structured this way

The repositories are separated by responsibility instead of being combined into a single monolith. That keeps the frontend, backend services, shared code, database evolution, and infrastructure concerns easier to reason about.

It also makes the public organization easier to browse: visitors can quickly see which repository handles which part of the system.

## Where to begin

- Developers starting locally should begin with the [`.wrapper`](https://github.com/Connect4-3D-Edition/.wrapper) repository for workspace setup, local environment instructions, and development tasks.
- New visitors who want the product-facing application can start with the [`frontend`](https://github.com/Connect4-3D-Edition/frontend) repository.
- Anyone trying to understand the backend split should look at [`service-api`](https://github.com/Connect4-3D-Edition/service-api), [`game-api`](https://github.com/Connect4-3D-Edition/game-api), and [`common-lib`](https://github.com/Connect4-3D-Edition/common-lib).
- The infrastructure and database repositories show how the supporting environment is organized behind the application.

This profile is intended as a high-level overview of the organization and its repositories.
