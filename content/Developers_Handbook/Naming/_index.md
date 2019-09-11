---
title: Naming
weight: 3
---

There are <a href="https://martinfowler.com/bliki/TwoHardThings.html" target="_blank">two hard things</a> in Computer Science, and the following is an attempt to ease our pain when naming things.

| What | Naming convention | Example |
| ---- | ----------------- | ------- |
| microservice | _functional description_ (+service) | A backend service |
| repository | _microservice name_ | a-backend-service |
| api specification | _microservice name_.yaml | a-backend-service.yaml |
| groupId | no.brreg._servicename_ | no.brreg.abackendservice |
| artifactId | _service-name_  | a-backend-service|
| package | _groupId_._funtion_ | no.brreg.abackendservice.api |
|         |                     | no.brreg.abackendservice.api.template|
| Api classes | _Microservice name_+Api  | ABackEndApi.java |
| Model classes | _Name of business object_  | ABackEnd.java |
| Controller classes | _Microservice name_+Controller | ABackEndController.java |
| Service classes | _Microservice name_ +Service | ABackEndService.java |
| Repository classes | _Microservice name_ +Service | ABackEndService.java |
| Util classes | _Microservice name_+_Util_ | ABackEndUtil.java |
