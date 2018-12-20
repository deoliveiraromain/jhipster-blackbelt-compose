# jhipster-blackbelt-compose

## Usage

Docker-compose file to run all Sample microservice :
- A microservice : [jhispter-blackbelt-service](https://github.com/deoliveiraromain/jhipster-blackbelt-service)
- A Gateway : [jhispter-blackbelt-gateway](https://github.com/deoliveiraromain/jhipster-blackbelt-gateway)
- JHispter Registry

First need to build jhispter-blackbelt-service and jhispter-blackbelt-gateway Docker images by running in each project :
```bash
mvnw package -Pprod verify jib:dockerBuild
```

And then, launch all your infrastructure by running: `docker-compose up -d`.

## Configured Docker services

### Service registry and configuration server:
- [JHipster Registry](http://localhost:8761)

### Applications and dependencies:
- gateway (gateway application) : http://localhost:8080/
- gateway's postgresql database : port 5432
- jhipsterBlackbelt (microservice application) :  http://localhost:/8095/ (not accessible outside of gateway)
- jhipsterBlackbelt's mongodb database : port 27017

### Additional Services:

To Deploy Registry to GAE : (after google cloud SDK install, connection, and project creation)

```bash
gcloud app deploy registry.yml
```

