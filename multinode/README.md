Starts TeamCity 2018.2.4 in docker-compose.

Don't forget to give at least 4Gb of RAM to your docker engine.

- Uses Postgres DB (`psql -p5433 -hlocalhost -Utest -dbuildserver`, password `test`)
- Starts 3 servers: primary, [running-builds node](https://confluence.jetbrains.com/display/TCD18/Configuring+Running+Builds+Node), [secondary node](https://confluence.jetbrains.com/display/TCD18/Configuring+Secondary+Node).
- And, one build agent

To start:

    docker-compose up

Next, open http://localhost:8111 for initial setup.

After creating a user, visit http://localhost:8111/agents.html?tab=unauthorizedAgents to authorize build agent.

To shutdown

    docker-compose down

For volumes and details see `docker-compose.yml`



