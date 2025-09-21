# Fullstack E-commerce Starter



## Run both frontend and backend together (development)

Install `concurrently` at the repo root and run both servers from one terminal:
```bash
# from project root
npm install
npm run start
```
This runs the backend on port 4000 and the frontend dev server on 5173.

## Docker (local development / simple deployment)

Build and run with docker-compose (creates a SQLite volume for the DB):
```bash
# from project root
docker-compose build
docker-compose up
```
- Backend will be available at http://localhost:4000/api
- Frontend will be available at http://localhost:5173 (served by nginx)

Notes:
- The Docker Compose setup uses a bind mount for the backend source so you can edit files live.
- Prisma + SQLite works with a file-based `dev.db` persisted to a Docker volume `db_data`. For production, we recommend using Postgres or MySQL and following Prisma's Docker guides: https://www.prisma.io/docs/guides/docker.

References used while composing these files:
- concurrently npm package documentation for running multiple scripts in parallel. (https://www.npmjs.com/package/concurrently)
- Vite build guide and examples for serving the built app with nginx. (https://vite.dev/guide/build)
- Prisma Docker guide for best practices with ORM and databases. (https://www.prisma.io/docs/guides/docker)
