# Prompt

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes.  Consider entrypoints, packaging, dependency libraries and start processes and if they are in the build file and sufficient to run the app as a container.

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes.  Consider entrypoints and start processes and if they are in the build file.  Exclude the absence of kubernetes specific and docker files in your considerations; these files will be added later.

You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes. If the build file includes spring-boot-start-parent, do not include it in your considerations.  Only consider dependencies explicitly described and if they support standalone startup.  Exclude the absence of kubernetes specific and docker files in your considerations; these files will be added later.

Build File =
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>1.2.3.RELEASE</version>
  </parent>
  <groupId>com.emc.data</groupId>
  <artifactId>data-import</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <name>data-import</name>
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
  		<plugin>
  			<groupId>org.springframework.boot</groupId>
  			<artifactId>spring-boot-maven-plugin</artifactId>
  		</plugin>
  	</plugins>
  </build>  
  <dependencies>
  	<dependency>
  		<groupId>org.springframework.boot</groupId>
  		<artifactId>spring-boot-starter-web</artifactId>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.boot</groupId>
  		<artifactId>spring-boot-starter-amqp</artifactId>
  	</dependency>
		<dependency>
			<groupId>org.webjars</groupId>
			<artifactId>bootswatch-paper</artifactId>
			<version>3.3.1+2</version>
		</dependency>

		<dependency>
			<groupId>org.webjars</groupId>
			<artifactId>jquery</artifactId>
			<version>2.1.3</version>
		</dependency>  </dependencies>
  <packaging>war</packaging>
</project>