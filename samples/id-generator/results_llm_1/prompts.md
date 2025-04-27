## Prompts

### Base

You are an expert software engineer.  Analyze the following build file and answer only 'yes' or 'no' if it describes an application that could be run on kubernetes.

= 'yes'

You are an expert software engineer.  Analyze the following build file and answer if it can be deployed on kubernetes and what part of the build file indicated that it could.

= 'no packaging highly unlikely' / spring integration means microservice so probably

You are an expert software engineer.  Analyze the following build file and answer only 'yes' or 'no' if the file provides sufficient information to determine if the app can be deployed on kubernetes.

= 'no'

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the file if the app can be deployed on kubernetes.

= '85%'

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes.  Consider entrypoints and start processes and if they are in the build file.

= '0'

### Shot

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example.code</groupId>
  <artifactId>id-generator</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <name>id-generator</name>
	<build>
		<plugins>
			<plugin>
				<artifactId>maven-compiler-plugin</artifactId>
				<configuration>
					<!-- <source>1.7</source>
					<target>1.7</target> -->
					<source>17</source>
					<target>17</target>					
				</configuration>
			</plugin>
		</plugins>
	</build>  
	<dependencies>
		<dependency>
			<groupId>org.springframework.integration</groupId>
			<artifactId>spring-integration-core</artifactId>
			<version>4.1.2.RELEASE</version>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-databind</artifactId>
			<version>2.4.4</version>
		</dependency>
	</dependencies>  
</project>