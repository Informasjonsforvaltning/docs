---
title: Java and Kotlin
weight: 3
---

## Recommended Java Implementations:
You can install the one of the versions listed below via SDKMAN or manually by following the installation guide on their website.

-- [Azul Zulu](https://www.azul.com/downloads/?package=jdk#zulu).

-- [Amazon Coretto](https://aws.amazon.com/corretto/?filtered-posts.sort-by=item.additionalFields.createdDate&filtered-posts.sort-order=desc)

-- [Eclipse Temurin from Adoptium](https://adoptium.net/).

## SDKMAN
You can easily install Java via [SDKMAN](https://sdkman.io/). After installation you can use the command `sdk list java` to see available java versions. The version you use depends on your context, meaning which app you are trying to use it in. Therefore, always refer to the version mentioned in the README.md file of the repository.
Other useful commands:

List available Java implementations
```bash
sdk list java
```

Installing Java OpenJDK version
```bash
sdk install java x.y.z-open
```

Switching between different java versions
```bash
sdk use java <version>
```  

Setting a default version
```bash
sdk default java <version>
```

## Maven
Maven can also be installed with SDKMAN or manually by following their installation guide:
https://maven.apache.org/install.html

### Installing maven with sdkman
```bash
sdk install maven x.y.z
```

### Running a maven project:
```bash
mvn clean install
```
