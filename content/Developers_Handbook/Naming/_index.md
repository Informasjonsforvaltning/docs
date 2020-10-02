---
title: Naming
weight: 3
---

There are [two hard things](https://martinfowler.com/bliki/TwoHardThings.html) in Computer Science, and the following is an attempt to ease our pain when naming things.

| What | Naming convention | Example |
| ---- | ----------------- | ------- |
| microservice | _functional description_ (+service) | A backend service |
| repository | _microservice name_ | a-backend-service |
| api specification | _microservice name_.yaml | a-backend-service.yaml |
| groupId | no.brreg._servicename_ | no.brreg.abackendservice |
| artifactId | _service-name_  | a-backend-service|
| package | _groupId_._funtion_ | no.brreg.abackendservice.api\|controller\|service\|repository\|model |
| Api classes | _name-of-resource-in-api-spec_+Api  | SomeResourceApi.java |
| Model classes | _name-of-resource-in-api-spec_+DB  | SomeResourceDB.java |
| Controller classes | _name-of-resource-in-api-spec_+ApiImpl.java | SomeResourceApiImpl.java |
| Service classes | _name-of-resource-in-api-spec_ +Service | SomeResourceService.java |
| Repository classes | _name-of-resource-in-api-spec_ +Repository | SomeResourceRepository.java |
