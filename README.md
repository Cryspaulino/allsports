# AllSports

AllSports is a full-stack sports discovery platform built with React, Vite, Tailwind CSS, Express, and Mongoose. It is structured like a production app and ships with seed data for global professional and college teams across men's and women's sports.

## Stack

- Frontend: React, Vite, Tailwind CSS, React Router, Axios
- Backend: Node.js, Express, Mongoose, REST APIs
- Data: Seed-backed sample dataset with optional MongoDB persistence

## Quick Start

1. Install dependencies from the workspace root:
   `npm install`
2. Optionally create `server/.env` from `server/.env.example` and set `MONGO_URI` if you want MongoDB-backed reads and seeding.
3. Start the client and server together:
   `npm run dev`

The frontend runs on `http://localhost:5173` and the API runs on `http://localhost:4000`.

## API Routes

- `GET /api/sports`
- `GET /api/sports/:sport`
- `GET /api/leagues`
- `GET /api/leagues/:league`
- `GET /api/teams`
- `GET /api/teams/:id`
- `GET /api/teams/search`
- `GET /api/teams/:id/roster`
- `GET /api/schedule`
- `GET /api/standings`

## Adding Data

The easiest place to extend the platform is `database/seedData.js`.

- Add a new sport to `sportCatalog`
- Add a new league to `leagues`
- Add a team with a matching `league_slug`
- Add players that reference the team `id`
- Add games that reference the home and away team ids

The frontend routes and filters will automatically surface the new data once the API restarts.

## MongoDB Seeding

If you want to persist sample data into MongoDB:

1. Create `server/.env` with a valid `MONGO_URI`
2. Run `npm run seed`

If no MongoDB connection is configured, the API still works by serving the built-in seed snapshot.
