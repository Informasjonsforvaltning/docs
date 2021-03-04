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

From Clemson "Testing Strategies in a Microservice Architecture" we have borrowed the following strategies:

- unit (solitary + sociable) _automated, included in coverage_
- integration (testing adapters, classes that communicates with the outside world) _automated, included in coverage_
- contract (based on specification, "service test", the artifact that will be deployed) _automated_
- end-to-end (minimal) _mostly manual_

_next step_  
As an alternative to end-to-end tests we prefer a technique called _semantic monitoring_, where we use fake events (_synthetic transactions_) to ensure that the system is behaving semantically.

Another aspect of testing is _timing_, when to run what tests:
![A standard release pipeline](./A_standard_release_process_as_pipeline.svg)

----------------------------------------
### References
- https://martinfowler.com/articles/microservice-testing/
- https://samnewman.io/books/building_microservices/
- https://martinfowler.com/bliki/SyntheticMonitoring.html
