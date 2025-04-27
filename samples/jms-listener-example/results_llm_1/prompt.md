# prompt

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes.  Consider entrypoints and start processes and if they are in the build file.

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
