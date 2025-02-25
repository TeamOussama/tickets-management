# Tickets

This app was created to manage tickets.

## Please follow next steps to run the app:

```
npm install -g @angular/cli
npm install
```

Run the database docker image, can be started as follows:

```
docker compose up
```

Run the development frontend, can be started as follows:

```
ng serve
```

Run the development backend, can be started as follows:

```
mvn clean package
mvn spring-boot:run -Dspring-boot.run.profiles=local
```

Your application is now accessible under `localhost:4200`.

**register with random email and password, and login to test the app.**


## Development

When starting the application `docker compose up` is called and the app will connect to the contained services.
[Docker](https://www.docker.com/get-started/) must be available on the current system.

During development it is recommended to use the profile `local`. In IntelliJ `-Dspring.profiles.active=local` can be
added in the VM options of the Run Configuration after enabling this property in "Modify options". Create your own
`application-local.properties` file to override settings for development.

Lombok must be supported by your IDE. For IntelliJ install the Lombok plugin and enable annotation processing.

In addition to the Spring Boot application, the development server must also be started - for this
[Node.js](https://nodejs.org/) version 22 is required. Angular CLI and required dependencies must be installed once:

use java 17.

## Testing requirements

Testcontainers is used for running the integration tests. Due
to the reuse flag, the container will not shut down after the tests. It can be stopped manually if needed.

Frontend unit tests can be executed with `ng test`.

## Build

The application can be tested and built using the following command:

```
mvnw clean package
```

Start your application with the following command - here with the profile `production`:

```
java -Dspring.profiles.active=production -jar ./target/tickets-0.0.1-SNAPSHOT.jar
```
y
If required, a Docker image can be created with the Spring Boot plugin. Add `SPRING_PROFILES_ACTIVE=production` as
environment variable when running the container.

```
mvnw spring-boot:build-image -Dspring-boot.build-image.imageName=com.hahn.api/tickets
```

## Further readings

* [Maven docs](https://maven.apache.org/guides/index.html)  
* [Spring Boot reference](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/)  
* [Spring Data JPA reference](https://docs.spring.io/spring-data/jpa/reference/jpa.html)
* [Learn Angular](https://angular.dev/tutorials/learn-angular)  
* [Angular CLI](https://angular.dev/tools/cli)
* [Tailwind CSS](https://tailwindcss.com/)  
