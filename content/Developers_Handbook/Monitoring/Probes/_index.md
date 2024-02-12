---
title: Probes
weight: 1
---
Probes should not require authorization.

Any http response code greater than or equal to `200` and less than `400` indicates success. Any other code indicates failure.

## Readiness

A containers's readiness probe is used to check whether the service is ready to accept connections.

Example:

```yaml
readinessProbe:
   httpGet:
      path: /readyz
      port: 8080
   initialDelaySeconds: 3
   periodSeconds: 30
   successThreshold: 1
   failureThreshold: 3
```

We should check if the runtime dependencies that the service absolutely need to function, is ready. If the service depends on a database, it should check if the database is ready.

## Liveness

A containers's liveness probe is used to check whether the service has gone into a broken state and should be restarted.

Example:

```yaml
livenessProbe:
   httpGet:
      path: /livez
      port: 8080
   initialDelaySeconds: 5
   periodSeconds: 30
   successThreshold: 1
   failureThreshold: 5
```

An implementation (in java/kotlin) would be simply

```Java
@RequestMapping(value = ["/ping"], method = [GET])

fun ping(): ResponseEntity<Void> =
        ResponseEntity.ok().build()
```

## References

The following is a nice intro for Spring Boot: <https://www.baeldung.com/spring-boot-kubernetes-self-healing-apps>  
Kubernetes configuration: <https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-probes/>  
Example with authorization: <https://www.critiqus.com/post/kubernetes-health/>  
