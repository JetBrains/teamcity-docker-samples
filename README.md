# TeamCity docker-compose samples [![JetBrains team project](http://jb.gg/badges/team.svg)](https://confluence.jetbrains.com/display/ALL/JetBrains+on+GitHub)

Simple [docker compose files](https://docs.docker.com/compose/compose-file/) to run TeamCity server together with agents.

## Images

TeamCity provides docker images for Linux and Windows containers. Windows images have the following suffixes in tags: `-nanoserver` and `-windowsservercore`. Available TeamCity images on Docker Hub:

* [jetbrains/teamcity-minimal-agent](https://hub.docker.com/r/jetbrains/teamcity-minimal-agent)
* [jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)
* [jetbrains/teamcity-server](https://hub.docker.com/r/jetbrains/teamcity-server)

## Basic configurations

Docker compose files for Linux containers are stored in `compose-ubuntu` directory, for Windows in `compose-windows`.

* Set TeamCity version in .env file (also could be 'EAP', or 'EAP-nanoserver-2004' for Windows). 
* To run, use: `docker-compose up -d` command
* After creating a user, visit ["Agents -> Unauthorized"](http://localhost:8112/agents.html?tab=unauthorizedAgents) to authorize the build agent.

After start TeamCity server will be available on `http://localhost:8112/` in Linux containers. 
To open server URL on Windows execute the following command in PowerShell:

```
explorer "http://$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' teamcitywindows_server_1):8111"
```

## Multi-node configuration with several servers

See README.md in [multinode folder](./multinode/)

