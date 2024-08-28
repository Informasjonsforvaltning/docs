---
title: Testing
weight: 4
---

On testing microservices and how we do it.

From Clemson "Testing Strategies in a Microservice Architecture" we have borrowed the following strategies:

- unit 
- integration
- component 
- contract
- end-to-end

Other types of testing we apply:
- security testing (DAST)
- performance testing (load testing)

### Unit testing
Unit testing is the practice of testing small pieces of code, typically individual functions or methods, in isolation from the rest of the codebase. The goal is to ensure that each unit of code works as expected. Unit tests are typically written by developers as they write the code itself, and are run frequently during the development process.

Unit tests are mainly run when building the application (backend application), and are included in the coverage report. The coverage report is used to ensure that the codebase is well tested, and to identify areas that may need additional testing.

Tools we use for testing:
- JUnit
- Mockito
- Mockk
- Pytest

### Integration testing
Integration testing is the practice of testing how different pieces of code work together. This can include testing how different modules or services interact with each other, or how a module or service interacts with an external system. The goal is to ensure that the different pieces of code work together as expected.

Integration tests are typically written by developers, and are run frequently during the development process. They are also run when building the application, and are included in the coverage report.

Tools we use for testing:
- JUnit for Java/Kotlin
- Testcontainers for Java/Kotlin
- Spring Boot Test for Java/Kotlin
- WireMock
- Pytest for Python
- Testing for Go
- Testify for Go
- Dockertest for Go

### Component testing
Component testing is mainly used for testing the frontend application. It is the practice of testing individual components of the application, such as buttons, forms, or other UI elements. The goal is to ensure that each component works as expected.

Component tests are typically written by developers, and are run frequently during the development process. They are also run when building the application.

Tools we use for testing:
- Jest
- React Testing Library

### Contract testing
Contract testing is the practice of testing how different services interact with each other. The goal is to ensure that the different services work together as expected. Contract tests are typically written by developers, and are run frequently during the development process. They are also run when building the application.

Contract tests are part of the backend application and are run in the CI/CD pipeline.

Tools we use for testing:
- JUnit
- Testcontainers
- WireMock
- Spring Boot Test
- Pytest

### End-to-end testing
End-to-end testing is the practice of testing the entire application, from the user interface to the backend services. The goal is to ensure that the application works as expected from the user's perspective. End-to-end tests are typically written by developers, and are run frequently during the development process. They are also run when building the application. 
These tests are part of the frontend application and are run in the CI/CD pipeline mainly against the staging environment.

Tools we use for testing:
- Playwright
- Cypress

Example of a test in Playwright:
https://github.com/Informasjonsforvaltning/catalog-frontend/tree/main/apps/service-catalog-e2e

### Security testing
Security testing is the practice of testing the application for security vulnerabilities. The goal is to ensure that the application is secure and that sensitive data is protected. Security tests are typically run automatically. They are also run when building the application.

Security testing is typically done using DAST (Dynamic Application Security Testing) tools. These tools scan the application for security vulnerabilities, such as SQL injection, cross-site scripting, and other common security issues. These tests are run against the staging environment.

Tools we use for security testing:
- Synopsys Polaris
- OWASP ZAP (manual testing)
- Burp Suite (manual testing)
 
### Performance testing
Performance testing is the practice of testing the application for performance issues. The goal is to ensure that the application performs well under load. Performance tests are typically run automatically. These tests are run against the staging environment and mainly executed manually.

Tools we use for performance testing:
- JMeter

----------------------------------------

### References

- <https://martinfowler.com/articles/microservice-testing/>
- <https://samnewman.io/books/building_microservices/>
- <https://martinfowler.com/bliki/SyntheticMonitoring.html>
- <https://playwright.dev/>
- <https://www.cypress.io/>
