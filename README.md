# Health Data Hub OAuth Authorization server

[![Build Status](https://travis-ci.org/AriHealth/hdh-oauth-authorization.svg?branch=master)](https://travis-ci.org/AriHealth/hdh-oauth-authorization) 
[![codecov.io](https://codecov.io/gh/AriHealth/hdh-oauth-authorization/branch/master/graphs/badge.svg)](http://codecov.io/gh/AriHealth/hdh-oauth-authorization)
[![Quality Gate](https://sonarcloud.io/api/project_badges/measure?project=net.atos.ari:hdh-oauth-authorization&metric=alert_status)](https://sonarcloud.io/dashboard/index/net.atos.ari:hdh-oauth-authorization)
[![Docker Build](https://img.shields.io/docker/cloud/build/arihealth/hdh-oauth-authorization)](https://cloud.docker.com/u/arihealth/repository/docker/arihealth/hdh-oauth-authorization)
[![Docker Pulls](https://img.shields.io/docker/pulls/arihealth/hdh-oauth-authorization)](https://cloud.docker.com/u/arihealth/repository/docker/arihealth/hdh-oauth-authorization)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](https://opensource.org/licenses/Apache-2.0)

## Description

Health Data Hub OAuth 2.0 Authorization server for testing to provide SMART on FHIR compliance. It exposes the API as it is defined in [RFC 6749](https://tools.ietf.org/html/rfc6749)

## Technology

- Java 8+
- Maven for Java dependency management
- Spring Boot
- Spring Security
- Spring OAuth
- Lombok for the models

## Functionalities

- Add two numbers without verification

## How to deploy

Compile and package the project with

```
mvn clean package
```

and execute

```
java -jar target/hdh-oauth-authorization.jar
```

It can also be run as:

```
mvn spring-boot:run
```

Go to your browser and type http://localhost:8085/swagger-ui.html

## Environment variables

    LOGGING_FOLDER=
    LOGGING_MODE=

## Docker deployment

Build the image:

```
docker build -t arihealth/hdh-oauth-authorization .
```

Simple deployment:

```
docker run --name hdh-oauth-authorization -d arihealth/hdh-oauth-authorization
```

Logging can be also configured using `LOGGING_FOLDER` and sharing a volume (this is useful for example for [ELK](https://www.elastic.co/elk-stack) processing). The level of the logging can be configured with `LOGGING_MODE` (dev|prod):

```
docker run --name hdh-oauth-authorization -d -v /tmp/log/hdh-oauth-authorization:/log/hdh-oauth-authorization -e LOGGING_FOLDER=/log/test -e LOGGING_MODE=dev health/hdh-oauth-authorization
```

## License

Apache 2.0

By downloading this software, the downloader agrees with the specified terms and conditions of the License Agreement and the particularities of the license provided.
