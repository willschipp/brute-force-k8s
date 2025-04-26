### Samples

[https://github.com/willschipp/spring-boot-admin]
[https://github.com/willschipp/spring-cloud-eureka-server] 
[https://github.com/willschipp/db-via-rest]
[https://github.com/willschipp/example-passing-profiles]
[https://github.com/willschipp/multi-tenant-orm]
[https://github.com/willschipp/jms-listener-example]
[https://github.com/willschipp/id-generator]
[https://github.com/willschipp/spring-xd-elasticsearch-sink]
[https://github.com/willschipp/data-import]
[https://github.com/willschipp/live-data-ingestion] --> old Java version (1.7) upgraded to 1.8 --


| SCM Link | Changes | Command Line Run Output | Container Build Output | Docker Run Output | Deployment Output |
|----------|---------|-------------------------|------------------------|-------------------|-------------------|
| ~~[https://github.com/willschipp/spring-boot-admin]~~ | (won't build) | - | - | - | -|
| [https://github.com/willschipp/live-data-ingestion] | modified pom.xml to 1.8 from 1.7 source and target | `java -jar live-data-ingestion-0.0.1-SNAPSHOT.jar` = no main manifest attribute | Success | `docker run --name quick -p 8080:8080 -d quick` = no main manifest attribute | - |
|~~[https://github.com/willschipp/data-import]~~| modified pom.xml to 1.8 from 1.7 source and target | (won't build) | - | - | - |
|~~[https://github.com/willschipp/spring-xd-elasticsearch-sink]~~ | (con't build) | - | - | - | - |
| [https://github.com/willschipp/id-generator] | modified pom.xml to 1.8 from 1.7 source and target | `java -jar id-generator-0.0.1-SNAPSHOT.jar` = no main manifest attribute | Success | `docker run --name quick -p 8080:8080 -d quick` = no main manifest attribute | - |
| ~~[https://github.com/willschipp/jms-listener-example]~~ | (won't build) | - | - | - | - |
| [https://github.com/willschipp/multi-tenant-orm] | none | `java -jar multi-userTenant-orm-1.0-SNAPSHOT.jar` = startup but fail due to external service availability | Success | `docker run --name quick -p 8080:8080 -d quick` = startup but fail due to external service availability | - |
| ~~[https://github.com/willschipp/example-passing-profiles]~~ | (won't build) | - | - | - | - |
| ~~[https://github.com/willschipp/db-via-rest]~~ | (won't build) | - | - | - | - |
| ~~[https://github.com/willschipp/spring-cloud-eureka-server]~~  | (won't build) | - | - | - | - |