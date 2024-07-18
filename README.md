# code-with-quarkus-oms

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: <https://quarkus.io/>.

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:

```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at <http://localhost:8080/q/dev/>.

## Packaging and running the application

The application can be packaged using:

```shell script
./mvnw package
```

It produces the `quarkus-run.jar` file in the `target/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `target/quarkus-app/lib/` directory.

The application is now runnable using `java -jar target/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:

```shell script
./mvnw package -Dquarkus.package.jar.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar target/*-runner.jar`.

## Creating a native executable

You can create a native executable using:

```shell script
./mvnw package -Dnative
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using:

```shell script
./mvnw package -Dnative -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./target/code-with-quarkus-oms-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult <https://quarkus.io/guides/maven-tooling>.

## Related Guides

- OpenShift ([guide](https://quarkus.io/guides/deploying-to-openshift)): Generate OpenShift resources from annotations
- REST ([guide](https://quarkus.io/guides/rest)): A Jakarta REST implementation utilizing build time processing and Vert.x. This extension is not compatible with the quarkus-resteasy extension, or any of the extensions that depend on it.
- Hibernate ORM ([guide](https://quarkus.io/guides/hibernate-orm)): Define your persistent model with Hibernate ORM and Jakarta Persistence
- REST Client - OpenID Connect Filter ([guide](https://quarkus.io/guides/security-openid-connect-client)): Use REST Client filter to get and refresh access tokens with OpenId Connect Client and send them as HTTP Authorization Bearer tokens
- Messaging - Kafka Connector ([guide](https://quarkus.io/guides/kafka-getting-started)): Connect to Kafka with Reactive Messaging
- YAML Configuration ([guide](https://quarkus.io/guides/config-yaml)): Use YAML to configure your Quarkus application
- Logging JSON ([guide](https://quarkus.io/guides/logging#json-logging)): Add JSON formatter for console logging
- Kubernetes ([guide](https://quarkus.io/guides/kubernetes)): Generate Kubernetes resources from annotations
- REST Client - OpenID Connect Token Propagation ([guide](https://quarkus.io/guides/security-openid-connect-client)): Use REST Client to propagate the incoming Bearer access token or token acquired from Authorization Code Flow as HTTP Authorization Bearer token
- JDBC Driver - PostgreSQL ([guide](https://quarkus.io/guides/datasource)): Connect to the PostgreSQL database via JDBC
- REST Jackson ([guide](https://quarkus.io/guides/rest#json-serialisation)): Jackson serialization support for Quarkus REST. This extension is not compatible with the quarkus-resteasy extension, or any of the extensions that depend on it
- Hibernate ORM with Panache ([guide](https://quarkus.io/guides/hibernate-orm-panache)): Simplify your persistence code for Hibernate ORM via the active record or the repository pattern

## Provided Code

### YAML Config

Configure your application with YAML

[Related guide section...](https://quarkus.io/guides/config-reference#configuration-examples)

The Quarkus application configuration is located in `src/main/resources/application.yml`.

### Hibernate ORM

Create your first JPA entity

[Related guide section...](https://quarkus.io/guides/hibernate-orm)

[Related Hibernate with Panache section...](https://quarkus.io/guides/hibernate-orm-panache)


### Messaging codestart

Use Quarkus Messaging

[Related Apache Kafka guide section...](https://quarkus.io/guides/kafka-reactive-getting-started)


### REST

Easily start your REST Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)
# Order Management System

## Description

This project is an Order Management System (OMS) developed using Java, Quarkus, and Kafka. It leverages MongoDB for data storage and is designed to manage orders, handle events, and integrate with other services using modern cloud-native technologies.

## Technologies Used

- **Java**
- **Quarkus**
- **Apache Kafka**
- **MongoDB**
- **Kubernetes / OpenShift (optional)**
- **REST API with JSON over HTTPS**

## Prerequisites

- Java 17 or higher
- Apache Kafka
- MongoDB
- Maven
- IntelliJ IDEA

## Project Structure

```plaintext
src
├── main
│   ├── java
│   │   ├── com.example.entity
│   │   │   └── Order.java
│   │   ├── com.example.repository
│   │   │   └── OrderRepository.java
│   │   ├── com.example.service
│   │   │   └── OrderService.java
│   │   ├── com.example.resource
│   │   │   └── OrderResource.java
│   │   ├── com.example.kafka
│   │   │   ├── OrderProducer.java
│   │   │   └── OrderConsumer.java
│   ├── resources
│   │   └── application.properties
└── test
    ├── java
    │   └── com.example
    │       └── OrderResourceTest.java
