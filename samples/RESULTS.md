# Result Capture


## Samples

| link | command line run | container run | llm probability | expectation |
| ---- | ---------------- | ------------- | --------------- | ----------- |
| [./data-import] | success | - | 50% | pass |
| [./db-via-rest] | fail without service | - | 70% | pass |
| [./example-passing-profiles] | success | - | 0% | pass |
| [./id-generator] | fail without main | - | 0% | fail |
| [./jms-listener-example] | fail without service | - | 70% | pass |
| [./live-data-ingestion] | fail without main | - | 70% | fail |
| [./multi-tenant-orm] | fail without service | - | 80% | pass |
| [./spring-cloud-eureka-server] | success | - | 95% | pass |
| [./spring-xd-elasticsearch-sink] | fail without main | - | 90% | fail |


## Advanced probability prompt

### Prompt

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes. If the build file includes spring-boot-start-parent, do not include it in your considerations.  Only consider dependencies explicitly described and if they support standalone startup.  Exclude the absence of kubernetes specific and docker files in your considerations; these files will be added later.


### Results

| link | command line run | container run | llm probability | expectation |
| ---- | ---------------- | ------------- | --------------- | ----------- |
| [./data-import] | success | - | 90% | pass |
| [./db-via-rest] | fail without service | - | 80% | pass |
| [./example-passing-profiles] | success | - | 95% | pass |
| [./id-generator] | fail without main | - | 0% | fail |
| [./jms-listener-example] | fail without service | - | 80% | pass |
| [./live-data-ingestion] | fail without main | - | 0% | fail |
| [./multi-tenant-orm] | fail without service | - | 80% | pass |
| [./spring-cloud-eureka-server] | success | - | 95% | pass |
| [./spring-xd-elasticsearch-sink] | fail without main | - | 0% | fail |


## Deployment Correct

### Prompt

You are an expert software engineer.  Analyze the following build file and create only a kubernetes deployment.yaml for it. Consider if an endpoint is provided by the build file to support a liveness or readiness probe, excluding them if there is not an explicity dependency.  Create placeholders for external service configuration based on any explicit dependencies in the build file.

BUILD_FILE=

| link | considerations | deployment yaml correct | 
| ---- | -------------- | ----------------------- |
| [./data-import] | RMQ variables, no liveness/readiness endpoints | yes |
| [./db-via-rest] | database variables, actuator means liveness/readiness endpoints | yes |
| [./example-passing-profiles] | - | yes |
| [./jms-listener-example] | AMQ variables, no liveness/readiness endpoints | yes |
| [./multi-tenant-orm] | database variables, no liveness/readiness endpoints | yes |
| [./spring-cloud-eureka-server] | - | yes |



## Conclusions

### Test data
- 9 apps all leveraging Java and Springframework
- variety of app roles ranging from web apps to component libraries (Spring XD/Spring Integration)
- some required external services to run successfully (e.g. database, RMQ/AMQ)

### Brute Force
- all apps containerize using a Common Dockerfile perspective
- all apps are then pushed to a registry and default deployment yaml used

#### Results

| link | k8s startup |
| ---- | ----------- | 
| [./data-import] | success |
| [./db-via-rest] | fail without service |
| [./example-passing-profiles] | success |
| [./id-generator] | fail without main |
| [./jms-listener-example] | fail without service |
| [./live-data-ingestion] | fail without main |
| [./multi-tenant-orm] | fail without service |
| [./spring-cloud-eureka-server] | success |
| [./spring-xd-elasticsearch-sink] | fail without main |

### LLM Approach
- apps are filtered for suitability
- dockerfiles are generated for those that are suitable
- deployment yamls are tailored to suitable apps

#### Results

| link | suitable | deployment yaml correct |
| ---- | -------- | ----------------------- |
| [./data-import] | yes | yes |
| [./db-via-rest] | yes | yes |
| [./example-passing-profiles] | yes | yes |
| [./id-generator] | no | N/A |
| [./jms-listener-example] | yes | yes |
| [./live-data-ingestion] | no | N/A |
| [./multi-tenant-orm] | yes | yes |
| [./spring-cloud-eureka-server] | yes | yes |
| [./spring-xd-elasticsearch-sink] | no | N/A |


### Result Summary

The LLM approach correctly identified workloads as to deployability on Kubernetes and created an appropriately configured deployment.yaml in each occurence.
The LLM approach managed to filter out workloads reducing initial dataset size from 9 to 6 (33% work reduction).
The LLM approach managed to create appropriate deployment yamls catering for liveness and readiness probes ensuring accurate kubernetes logging of failures


### Next Steps

- expand process to include compiled JAR files and analysis of any properties files included
- use compiled java classes for analysis (`cat *.class | base64 | ["convert to an uncompiled java class"])
