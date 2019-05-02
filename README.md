# TeamCity docker-compose samples [![JetBrains team project](http://jb.gg/badges/team.svg)](https://confluence.jetbrains.com/display/ALL/JetBrains+on+GitHub)

Simple [docker compose files](https://docs.docker.com/compose/compose-file/) to run TeamCity server together with agents.

## Images

TeamCity provides docker images for Linux and Windows containers. Windows images have the following suffixes in tags: `-nanoserver` and `-windowsservercore`. Available TeamCity images on Docker Hub:

* [jetbrains/teamcity-minimal-agent](https://hub.docker.com/r/jetbrains/teamcity-minimal-agent)
* [jetbrains/teamcity-agent](https://hub.docker.com/r/jetbrains/teamcity-agent)
* [jetbrains/teamcity-server](https://hub.docker.com/r/jetbrains/teamcity-server)

## Basic configurations

Docker compose files for Linux containers are stored in `compose-ubuntu` directory, for Windows in `compose-windows`.

* To run latest release use: `docker-compose up -d`
* To run latest EAP use: `docker-compose -f docker-compose.yml -f docker-compose.eap.yml up -d`

After start TeamCity server will be available on `http://localhost:8112/` in Linux containers. To open server URL on Windows execute the following command in PowerShell:

```
explorer "http://$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' teamcitywindows_server_1):8111"
```

## Multi-node configuration with several servers

See README.md in [multinode folder](./multinode/)

