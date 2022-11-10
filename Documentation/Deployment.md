# Deployment
## Server Needed
- Everything for eFinPlan can be run on Docker. Install Docker and then run `docker compose up` in the root directory, where `docker-compose.yml` is.
## Where to put Files and Folders
- Simply download the zip of eFinPlan from the repo and extract. The placement does not matter; the Docker composition takes care of hosting.
## Start andStop System
- Install Docker and then run `docker compose up` in the root directory, where `docker-compose.yml` is. To stop, run `docker-compose stop`.
## Troubleshooting
- If something goes wrong, Docker Desktop allows you to click on the composition and view each container. From there, you can see the container that has errored and view what the message is. Additionally, the CLI for Docker also describes errors after running `docker compose up`.
## Source of Errors
- The error messages sent by Docker state the container and reason for failure. From this, you can determine the error.
## Critical or Vulnerable Pieces
- Failure could arise from the backend, as it is not CORS secured due to being made as a local web app. The database uses the official Postgres image, so errors should be minimal. The frontend runs using Vite's built in server. The frontend is not fully built before running, as the nature of eFinPlan means that a locally-hosted dev server on the container will suffice. Therefore, the backend is the most likely place for failure. 
