# VProfile Web Application

vprofile is a Java web application packaged as a WAR file. It uses Spring Framework and Spring Security with JSP views, JPA/Hibernate persistence, MySQL, RabbitMQ, Memcached, and Elasticsearch.

## Requirements

- Java 17 or newer
- Maven 3.8+
- MySQL
- RabbitMQ
- Memcached
- Elasticsearch 7.x

Docker definitions for the application, database, and web server are available in [`Docker-files/`](Docker-files/).

## Build and test

```bash
mvn clean verify
```

The generated WAR file is written to `target/`.

## Run locally

1. Start the required supporting services.
2. Update the connection settings in [`src/main/resources/application.properties`](src/main/resources/application.properties) for your environment.
3. Build the application with Maven.
4. Deploy the generated WAR to a Jakarta EE 10-compatible servlet container.

Do not commit passwords, tokens, or other environment-specific credentials. Use local configuration or environment-specific secret management for development and deployments.

## CI/CD

The GitHub Actions workflow in [`.github/workflows/ci.yml`](.github/workflows/ci.yml) builds and tests pull requests, runs Checkstyle and SonarQube analysis, and builds and publishes the application Docker image on pushes to `main`.

