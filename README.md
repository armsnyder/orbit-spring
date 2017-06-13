Orbit Spring Integration
============
[![Release](https://img.shields.io/github/release/orbit/orbit-spring.svg)](https://github.com/orbit/orbit-spring/releases)
[![Maven Central](https://img.shields.io/maven-central/v/cloud.orbit/orbit-spring.svg)](https://repo1.maven.org/maven2/cloud/orbit/orbit-spring/)
[![Javadocs](https://img.shields.io/maven-central/v/cloud.orbit/orbit-spring.svg?label=javadocs)](http://www.javadoc.io/doc/cloud.orbit/orbit-spring)
[![Build Status](https://img.shields.io/travis/orbit/orbit-spring.svg)](https://travis-ci.org/orbit/orbit-springr)
[![Gitter](https://img.shields.io/badge/style-Join_Chat-ff69b4.svg?style=flat&label=gitter)](https://gitter.im/orbit/orbit?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Integration for using the Spring Framework to manage an Orbit Cluster.

## Actuator Support

Orbit Spring provides autoconfigured contributors to the 
[Spring Boot Actuator](https://github.com/spring-projects/spring-boot/tree/master/spring-boot-actuator) endpoints, which activate
if Spring Boot Actuator is found in your project classpath. Spring Boot Actuator is an optional dependency of Orbit Spring.

### Health Indicator

The
[OrbitHealthIndicator](https://github.com/orbit/orbit-spring/blob/master/src/main/java/cloud/orbit/spring/actuate/OrbitHealthIndicator.java)
is a
[HealthIndicator](https://github.com/spring-projects/spring-boot/tree/v1.5.4.RELEASE/spring-boot-actuator/src/main/java/org/springframework/boot/actuate/health/HealthIndicator.java) 
which contributes a health status of "UP" if the
[Stage](https://github.com/orbit/orbit/blob/master/actors/runtime/src/main/java/cloud/orbit/actors/Stage.java)
is running and the local node is alive. The health details are listed under the key "orbit" in the
[health endpoint](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-endpoints.html#production-ready-health).

```json
{
    "status": "UP",
    "orbit": {
        "status": "UP",
        "state": "RUNNING",
        "alive": true
    }
}
```

Developer & License
======
This project was developed by [Electronic Arts](http://www.ea.com) and is licensed under the [BSD 3-Clause License](LICENSE).
