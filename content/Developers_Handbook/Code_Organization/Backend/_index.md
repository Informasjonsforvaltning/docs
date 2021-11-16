---
title: Back-end
weight: 2
---


For our "back-end" services implemented in java/kotlin, a typical folder structure should be:

```sHELL
tree -L 6 --dirsfirst -I 'target'
.
├── src
│   ├── main
│   │   ├── java
│   │   │   └── no
│   │   │       ├── brreg
│   │   │       │   └── Generated.java
│   │   │       └── template
│   │   │           ├── model
│   │   │           ├── spring
│   │   │           └── Application.java
│   │   ├── kotlin
│   │   │   └── no
│   │   │       └── template
│   │   │           ├── controller
│   │   │           ├── jena
│   │   │           ├── mapping
│   │   │           ├── repository
│   │   │           └── service
│   │   └── resources
│   │       ├── openAPI
│   │       │   └── openapi-generator-maven-plugin
│   │       │       └── templates
│   │       ├── specification
│   │       │   └── template.yaml
│   │       ├── application.properties
│   │       ├── banner.txt
│   │       └── gitBranchName.sh
│   └── test
│       ├── java
│       │   └── no
│       │       └── template
│       │           ├── controller
│       │           ├── integration
│       │           ├── service
│       │           └── TestResponseReader.java
│       ├── kotlin
│       │   └── no
│       │       └── template
│       │           └── TestData.kt
│       └── resources
│           ├── mockito-extensions
│           │   └── org.mockito.plugins.MockMaker
│           └── responses
│               ├── example.ttl
├── buildCommands.sh
├── docker-compose.yml
├── Dockerfile
├── Jenkinsfile
├── pom.xml
├── README.md
├── TODO.md
```

 A reference implementation is here: <https://github.com/Informasjonsforvaltning/a-back-end-service>
