# prompt

You are an expert software engineer.  Analyze the following build file and create only a kubernetes deployment.yaml for it. Consider if an endpoint is provided by the build file to support a liveness or readiness probe, excluding them if there is not an explicity dependency.  Create placeholders for external service configuration based on any explicit dependencies in the build file.

BUILD_FILE=
plugins {
    id 'java'
    id 'org.springframework.boot' version '2.1.7.RELEASE'
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
    compile('org.springframework.boot:spring-boot-starter-web')
    testCompile('org.springframework.boot:spring-boot-starter-test')
    testCompile('org.apache.commons:commons-lang3:3.9')

}