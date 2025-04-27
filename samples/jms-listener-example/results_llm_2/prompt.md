You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes. If the build file includes spring-boot-start-parent, do not include it in your considerations.  Only consider dependencies explicitly described and if they support standalone startup.  Exclude the absence of kubernetes specific and docker files in your considerations; these files will be added later.

Build File =
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
