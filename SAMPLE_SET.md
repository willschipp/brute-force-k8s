### Samples


| SCM Link | Changes | Command Line Run Output | Container Build Output | Docker Run Output | Deployment Output |
|----------|---------|-------------------------|------------------------|-------------------|-------------------|
| ~~[https://github.com/willschipp/spring-boot-admin]~~ | (won't build) | - | - | - | -|
| [https://github.com/willschipp/live-data-ingestion] | modified pom.xml to 1.8 from 1.7 source and target | `java -jar live-data-ingestion-0.0.1-SNAPSHOT.jar` = no main manifest attribute | Success | `docker run --name quick -p 8080:8080 -d quick` = no main manifest attribute | - |
|[https://github.com/willschipp/data-import]| `brute-force-fixes` includes library version updates to compile starts up normally and runs | Success | starts up normally and runs | - |
|[https://github.com/willschipp/spring-xd-elasticsearch-sink] | `brute-force-fixes` includes library version updates to compile | jar to be installed in a framework | Success | - | - |
| [https://github.com/willschipp/id-generator] | modified pom.xml to 1.8 from 1.7 source and target | `java -jar id-generator-0.0.1-SNAPSHOT.jar` = no main manifest attribute | Success | `docker run --name quick -p 8080:8080 -d quick` = no main manifest attribute | - |
| [https://github.com/willschipp/jms-listener-example] | `brute-force-fixes` includes library version updates to compile | starts up normally and runs | Success | starts up normally and runs | - |
| [https://github.com/willschipp/multi-tenant-orm] | none | `java -jar multi-userTenant-orm-1.0-SNAPSHOT.jar` = startup but fail due to external service availability | Success | `docker run --name quick -p 8080:8080 -d quick` = startup but fail due to external service availability | - |
| [https://github.com/willschipp/example-passing-profiles]  | `brute-force-fixes` includes library version updates to compile | starts up normally and runs | Success | starts up normally and runs | - |
| [https://github.com/willschipp/db-via-rest] | `brute-force-fixes` includes library version updates to compile | starts up normally and runs | Success | starts up normally and runs | - |
| [https://github.com/willschipp/spring-cloud-eureka-server]  | `brute-force-fixes` includes library version updates to compile | starts up normally and runs | Success | starts up normally and runs | - |