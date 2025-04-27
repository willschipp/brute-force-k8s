# prompt

You are an expert software engineer.  Analyze the following build file and generate only a Dockerfile using the most appropriate FROM image from the following list; 'openjdk:24-ea-16-jdk-slim-bullseye','node:latest','python-3.12.10:slim-bullseye'.  If the application is in C#, use a microsoft image."

You are an expert software engineer.  Analyze the following build file and create only a kubernetes deployment.yaml for it. Consider if an endpoint is provided by the build file to support a liveness or readiness probe, excluding them if there is not an explicity dependency.  Create placeholders for external service configuration based on any explicit dependencies in the build file.

BUILD_FILE=
plugins {
    id 'java'
    id 'org.springframework.boot' version '2.3.0.RELEASE'
}

apply plugin: 'java'
apply plugin: 'io.spring.dependency-management'

group 'com.example'
version '1.0-SNAPSHOT'

sourceCompatibility = 1.8

repositories {
    mavenCentral()
}

dependencies {
	//data work
    compile('org.springframework.boot:spring-boot-starter-data-jpa')    
    compile('org.springframework.boot:spring-boot-starter-data-rest')
    compile('com.h2database:h2')
    //actuator
    compile('org.springframework.boot:spring-boot-starter-actuator')
    //cloud
    compile('org.springframework.cloud:spring-cloud-starter-netflix-eureka-client:2.2.4.RELEASE')
    //test work 
    testCompile('org.springframework.boot:spring-boot-starter-test')
}