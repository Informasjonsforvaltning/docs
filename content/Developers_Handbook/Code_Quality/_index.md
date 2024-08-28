---
title: Code quality
weight: 6
---

Code quality is a measure of how well the code is written, how well it is structured, how well it is documented, how well it is tested, how well it is reviewed, and how well it is maintained.

Code quality can be divided into the following categories:
 
- Code style/structure
- Coverage (testing)
- Security

## Code style/structure
Code style and structure are important for readability, maintainability, and collaboration. We use IDE plugins and linters to enforce code style and structure. 

We use the following tools:

- ESLint for JavaScript/Typescript
- Prettier for JavaScript/Typescript
- Intellij IDEA for Java/Kotlin
- Black for Python
- MyPy for Python

## Coverage (testing)
Code coverage is a measure of how much of the code is tested. We aim for 100% code coverage. 

We use the following tools:

- Codecov (not supported for Rust)
- Jacoco for Java/Kotlin
- Coverage.py for Python
- Pytest-cov for Python

## Security
Security is important for protecting the system and the data. We use security tools to scan the code for vulnerabilities.

We use the following tools:

- Dependabot
- Pip-audit for Python
- Npm-audit for JavaScript/Typescript
- Github Security Alerts (CodeQL, Dependabot)
- Synopsys Polaris (DAST)
- Trivy for Docker images
