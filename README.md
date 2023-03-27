# adempiere-zk-ui

<p align="center">
  <a href="https://adoptium.net/es/temurin/releases/?version=11">
    <img src="https://badgen.net/badge/Java/11/orange" alt="Java">
  </a>
  <a href="https://github.com/adempiere/adempiere-zk-ui/actions/workflows/build.yml">
    <img src="https://github.com/adempiere/adempiere-zk-ui/actions/workflows/build.yml/badge.svg" alt="Build GH Action">
  </a>
  <a href="https://github.com/adempiere/adempiere-zk-ui/blob/master/LICENSE">
    <img src="https://img.shields.io/badge/license-GNU/GPL%20(v2)-blue" alt="License">
  </a>
  <a href="https://github.com/adempiere/adempiere-zk-ui/releases/latest">
    <img src="https://img.shields.io/github/release/adempiere/adempiere-zk-ui.svg" alt="GitHub release">
  </a>
  <a href="https://discord.gg/T6eH6A7PJZ">
    <img src="https://badgen.net/badge/discord/join%20chat" alt="Discord">
  </a>
</p>

A swing User Interface based in adempiere box

This project just treat of run ADempiere ZK UI based on base adempiere box project using gradle

## Requirements

This project is a java client using swing interface and completely based on gradle package management

The follow requirements need for run it:

- [Java 11 or higher](https://adoptopenjdk.net/)
- [Gradle](https://gradle.org/install/)

## Runing as development
### Clean
```shell
gradle clean
```

### Execute ZK-UI with jetty lugin
With default connection properties file (`$HOME/Adempiere.properties`)
```shell
gradle appRun
```

```shell
# As System Property
gradle appRun -DPropertyFile=/tmp/TEMPLATE.properties
```


## Generate war file

You can generate a war file using the follow command

```shell
# As System Property
gradle war
```

This will be generated in `adempiere-zk-ui/build/libs/adempiere-zk-ui.war`


## Run with Docker

```Shell
docker pull openls/adempiere-middleware:alpine
```

### Minimal Docker Requirements
To use this Docker image you must have your Docker engine version greater than or equal to 3.0.

### Environment variables
- `ADEMPIERE_DB_TYPE`: Database Type (Supported `Oracle` and `PostgreSQL`). Default `PostgreSQL`
- `ADEMPIERE_DB_SERVER`: Hostname for data base server. Default: `localhost`
- `ADEMPIERE_DB_PORT`: Port used by data base server. Default: `5432`
- `ADEMPIERE_DB_NAME`: Database name that zk service will use to connect with the database. Default: `adempiere`
- `ADEMPIERE_DB_USER`: Database user that zk service will use to connect with the database. Default: `adempiere`
- `ADEMPIERE_DB_PASSWORD`: Database password that zk service will use to connect with the database. Default: `adempiere`

You can download the last image from docker hub, just run the follow command:

```Shell
docker run -d -p 8888:8888 --name shw-adempiere-zk-ui-complete -e ADEMPIERE_DB_SERVER="20.12.0.23" marcalwestf/shw-adempiere-zk-ui-complete:jetty-alpine-aero-rs-1.0.0
```

## Run it

Just go to `docker-compose` folder and run it

```Shell
cd docker-compose
```

```Shell
docker compose up
```

### Some Variables

You can change variables editing the `.env` file. Note that this file have a minimal example.
