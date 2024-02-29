# cnj-persistence-sql-backend-micro

Cloud native MicroProfile backend using JPA-based persistence to persist its domain model in a PostgreSQL database.

The application is packaged as a multi-architecture docker image which supports the following platforms:
* linux/amd64
* linux/arm64/v8

## Synopsis

This showcase demonstrates
* how to integrate relational databases in Spring Boot application using JPA
* how to create evolve relational database schemas using FlyWay**

### Extensions to JPA

Although JPA is a great way to bind data from relational databases to Java applications, the JPA is still missing some
features like auditable entities etc. In order to add these features to JPA compliant applications, this showcase is
depending on the CloudTrain library `cnj-common-persistence-jakarta`.
See GitHub repo [cnj-common-persistence-jakarta](https://github.com/msgoat/cnj-common-persistence-jakarta) for details.

### Database schema management

The SQL files to create and update the database schema are part of the application code at `/src/main/resources/db.migration`.
Since MicroProfile does not have any support of database migrations during application start, the startup bean
[FlywayDatabaseAutoMigrator](src/main/java/group/msg/at/cloud/cloudtrain/adapter/persistence/migration/FlywayDatabaseAutoMigrator.java)
has to do all the heavy lifting.

## Status

![Build Status](https://codebuild.eu-west-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiS0w4OGNSVFdmUlVraHlobDI5eGJYWk1nRW9aSThTb3U0RGpZLzMzczlWUE5TWEJQWVFNUkUvRngvT2doK0RsYXlZV2xqcFZ5NmJpRUhFazdCcWZGclQwPSIsIml2UGFyYW1ldGVyU3BlYyI6Ik9RbWpkVU0wRjRwd3VWWCsiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=main)

## Release information

Check [changelog](changelog.md) for latest version and release information.

## Docker Pull Command

`docker pull docker.cloudtrain.aws.msgoat.eu/cloudtrain/cnj-persistence-sql-backend-micro`

## Helm Pull Command

`helm pull oci://docker.cloudtrain.aws.msgoat.eu/cloudtrain-charts/cnj-persistence-sql-backend-micro`

## HOW-TO build this application locally

If all prerequisites are met, just run the following Maven command in the project folder:

```shell 
mvn clean verify -P pre-commit-stage
```

Build results: a Docker image containing the showcase application.

## HOW-TO start and stop this showcase locally

In order to run the whole showcase locally, just run the following docker commands in the project folder:

```shell 
docker compose up -d
docker compose logs -f 
```

Press `Ctlr+c` to stop tailing the container logs and run the following docker command to stop the showcase:

```shell 
docker compose down
```

## HOW-TO demo this showcase

The showcase application will be accessible:
* locally via `http://localhost:38080`
* remotely via `https://train2023-dev.k8s.cloudtrain.aws.msgoat.eu/cloudtrain/cnj-persistence-sql-backend-micro` (if the training cluster is up and running)

The OpenAPI specification of the exposed REST API is available at URI `/openapi`.
