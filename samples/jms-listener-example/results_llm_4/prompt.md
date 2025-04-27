# prompt

You are an expert software engineer.  Analyze the following build file and propertiess file and create only a kubernetes deployment.yaml for it. Consider if an endpoint is provided by the build file to support a liveness or readiness probe, excluding them if there is not an explicity dependency.  Create placeholders for external service configuration based on any explicit dependencies in the build file.

BUILD_FILE=
plugins {
    id 'java'
    id 'org.springframework.boot' version '2.1.3.RELEASE'
}

apply plugin: 'io.spring.dependency-management'

group 'io.platformconsulting'
version '1.0-SNAPSHOT'

sourceCompatibility = 1.8

repositories {
    mavenCentral()
}

dependencies {
    compile 'org.springframework.boot:spring-boot-starter-activemq'
    testCompile 'org.springframework.boot:spring-boot-starter-test'
}


PROPERTIES_FILE=
spring:
  activemq:
    broker-url: vm://embedded?broker.persistent=false,useShutdownHook=false
    in-memory: true
    queue:
      name: foo.bar
      selector: customheader = 'hiya'
  jms:
    listener:
      acknowledge-mode: auto
      auto-startup: true
    template:
      default-destination: foo.bar

