# Prompt

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes.  Consider entrypoints and start processes and if they are in the build file.

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
