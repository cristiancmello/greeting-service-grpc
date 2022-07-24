# Greeting Service gRPC

An example with Interface Proto, Server and Client using Java 11, Maven and Spring Boot.
You need an example with Interface Proto as external project and package? You will have an excellent day with me 🤗.

## Build and Installing Interface Protobuffers into your M2 folder

Very useful for development.

```sh
cd greeting-grpc-interfaceproto
mvn install
```

Example:

```sh
cd greeting-grpc-interfaceproto
mvn install
...
[INFO]
[INFO] --- maven-install-plugin:2.4:install (default-install) @ greeting-grpc-interfaceproto ---
[INFO] Installing C:\Users\cristian\Workspace\greeting-service-grpc\greeting-grpc-interfaceproto\target\greeting-grpc-interfaceproto-0.0.1-SNAPSHOT.jar to C:\Users\cristian\.m2\repository\com\greeting\grpc\greeting-grpc-interfaceproto\0.0.1-SNAPSHOT\greeting-grpc-interfaceproto-0.0.1-SNAPSHOT.jar
[INFO] Installing C:\Users\cristian\Workspace\greeting-service-grpc\greeting-grpc-interfaceproto\pom.xml to C:\Users\cristian\.m2\repository\com\greeting\grpc\greeting-grpc-interfaceproto\0.0.1-SNAPSHOT\greeting-grpc-interfaceproto-0.0.1-SNAPSHOT.pom
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  2.597 s
[INFO] Finished at: 2022-07-24T17:30:48-03:00
[INFO] ------------------------------------------------------------------------
```

* The **JAR package** `greeting-grpc-interfaceproto-0.0.1-SNAPSHOT.jar` placed in `~\.m2\repository\com\greeting\grpc\greeting-grpc-interfaceproto`

## Build and Running gRPC Server

```sh
cd greeting-grpc-server
mvn spring-boot:run
```

Example:

```sh
mvn spring-boot:run
[INFO] Scanning for projects...
...
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.2)

2022-07-24 17:37:35.090  INFO 14924 --- [           main] c.g.grpc.server.ServerApplication        : Starting ServerApplication using Java 17.0.2 on DESKTOP-DD441H2 with PID 14924 (C:\Users\cristian\Workspace\greeting-service-grpc\greeting-grpc-server\target\classes started by cristian in C:\Users\cristian\Workspace\greeting-service-grpc\greeting-grpc-server)
2022-07-24 17:37:35.091  INFO 14924 --- [           main] c.g.grpc.server.ServerApplication        : No active profile set, falling back to 1 default profile: "default"
2022-07-24 17:37:35.401  INFO 14924 --- [           main] g.s.a.GrpcServerFactoryAutoConfiguration : Detected grpc-netty-shaded: Creating ShadedNettyGrpcServerFactory
2022-07-24 17:37:35.575  INFO 14924 --- [           main] n.d.b.g.s.s.AbstractGrpcServerFactory    : Registered gRPC service: com.greeting.grpc.server.GreetingService, bean: greetingServiceImpl, class: com.greeting.grpc.server.GreetingServiceImpl
2022-07-24 17:37:35.576  INFO 14924 --- [           main] n.d.b.g.s.s.AbstractGrpcServerFactory    : Registered gRPC service: grpc.health.v1.Health, bean: grpcHealthService, class: io.grpc.protobuf.services.HealthServiceImpl
2022-07-24 17:37:35.576  INFO 14924 --- [           main] n.d.b.g.s.s.AbstractGrpcServerFactory    : Registered gRPC service: grpc.reflection.v1alpha.ServerReflection, bean: protoReflectionService, class: io.grpc.protobuf.services.ProtoReflectionService
2022-07-24 17:37:35.692  INFO 14924 --- [           main] n.d.b.g.s.s.GrpcServerLifecycle          : gRPC Server started, listening on address: *, port: 8080
2022-07-24 17:37:35.699  INFO 14924 --- [           main] c.g.grpc.server.ServerApplication        : Started ServerApplication in 0.808 seconds (JVM running for 1.005)
```

* The gRPC Server is **listening the port 8080**

## Build and Running gRPC Client

This example execute only Spring Boot's command line runner 

```sh
cd greeting-grpc-client
mvn spring-boot:run
```

Example:

```sh
mvn spring-boot:run
[INFO] Scanning for projects...
[INFO]
[INFO] ---------------< com.greeting.grpc:greeting-grpc-client >---------------
[INFO] Building greeting-grpc-client 0.0.1-SNAPSHOT
[INFO] --------------------------------[ jar ]---------------------------------
...
  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::                (v2.7.2)

2022-07-24 17:41:38.448  INFO 15272 --- [           main] c.g.g.g.GreetingGrpcClientApplication    : Starting GreetingGrpcClientApplication using Java 17.0.2 on DESKTOP-DD441H2 with PID 15272 (C:\Users\cristian\Workspace\greeting-service-grpc\greeting-grpc-client\target\classes started by cristian in C:\Users\cristian\Workspace\greeting-service-grpc\greeting-grpc-client)
2022-07-24 17:41:38.450  INFO 15272 --- [           main] c.g.g.g.GreetingGrpcClientApplication    : No active profile set, falling back to 1 default profile: "default"
2022-07-24 17:41:38.741  INFO 15272 --- [           main] n.d.b.g.c.a.GrpcClientAutoConfiguration  : Detected grpc-netty-shaded: Creating ShadedNettyChannelFactory + InProcessChannelFactory
2022-07-24 17:41:38.962  INFO 15272 --- [           main] c.g.g.g.GreetingGrpcClientApplication    : Started GreetingGrpcClientApplication in 0.752 seconds (JVM running for 0.954)
2022-07-24 17:41:39.233  INFO 15272 --- [           main] c.g.g.g.GreetingGrpcClientApplication    : Cristian have a dog called Lully and ?? your dog
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```

* Verify the output `Cristian have a dog called Lully and ?? your dog` (`??` = ❤️ sorry my log encoding 😞)
