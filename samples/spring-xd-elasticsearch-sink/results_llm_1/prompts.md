## Prompt


answer_1.json You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the file if the app can be deployed on kubernetes.

answer_2.json You are an expert software engineer.  Analyze the following build file and answer with only the probability in percentage if the application built using it can be deployed on kubernetes.  Consider entrypoints and start processes and if they are in the build file.


## Code

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <parent>
    <groupId>org.springframework.xd</groupId>
    <artifactId>spring-xd-module-parent</artifactId>
    <version>1.2.0.RELEASE</version>
  </parent>
  <groupId>com.emc.code</groupId>
  <artifactId>spring-xd-elasticsearch-sink</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <name>spring-xd-elasticsearch-sink</name>
  <build>
  	<plugins>
  		<plugin>
  			<artifactId>maven-compiler-plugin</artifactId>
  			<configuration>
  				<source>1.7</source>
  				<target>1.7</target>
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
  		<groupId>org.elasticsearch</groupId>
  		<artifactId>elasticsearch</artifactId>
  		<version>1.6.0</version>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.boot</groupId>
  		<artifactId>spring-boot-starter-test</artifactId>
  		<scope>test</scope>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.integration</groupId>
  		<artifactId>spring-integration-core</artifactId>
  	</dependency>
  	<dependency>
  		<groupId>com.fasterxml.jackson.core</groupId>
  		<artifactId>jackson-databind</artifactId>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.boot</groupId>
  		<artifactId>spring-boot-starter-logging</artifactId>
  	</dependency>
  </dependencies>
  <repositories>
  	<repository>
  		<id>spring-milestone</id>
  		<url>http://repo.spring.io/libs-release</url>
  	</repository>
  </repositories>
</project>



## Compile update

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  <!-- <parent>
    <groupId>org.springframework.xd</groupId>
    <artifactId>spring-xd-module-parent</artifactId>
    <version>1.2.0.RELEASE</version>
  </parent> -->
  <parent>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-parent</artifactId>
    <version>3.4.5</version>
  </parent>  
  <groupId>com.emc.code</groupId>
  <artifactId>spring-xd-elasticsearch-sink</artifactId>
  <version>0.0.1-SNAPSHOT</version>
  <name>spring-xd-elasticsearch-sink</name>
  <build>
  	<plugins>
  		<plugin>
  			<artifactId>maven-compiler-plugin</artifactId>
  			<!-- <configuration>
  				<source>1.7</source>
  				<target>1.7</target>
  			</configuration> -->
			<configuration>
  				<source>17</source>
  				<target>17</target>
  			</configuration>			
  		</plugin>
  		<plugin>
  			<groupId>org.springframework.boot</groupId>
  			<artifactId>spring-boot-maven-plugin</artifactId>
			<executions>
				<execution>
				<id>repackage</id>
				<goals>
					<goal>repackage</goal>
				</goals>
				<configuration>
					<layout>NONE</layout>
					<classifier>exec</classifier>
				</configuration>
				</execution>
			</executions>			
  		</plugin>
  	</plugins>
  </build>
  <dependencies>
  	<dependency>
  		<groupId>org.elasticsearch</groupId>
  		<artifactId>elasticsearch</artifactId>
  		<version>1.6.0</version>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.boot</groupId>
  		<artifactId>spring-boot-starter-test</artifactId>
  		<scope>test</scope>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.integration</groupId>
  		<artifactId>spring-integration-core</artifactId>
  	</dependency>
  	<dependency>
  		<groupId>com.fasterxml.jackson.core</groupId>
  		<artifactId>jackson-databind</artifactId>
  	</dependency>
  	<dependency>
  		<groupId>org.springframework.boot</groupId>
  		<artifactId>spring-boot-starter-logging</artifactId>
  	</dependency>

	<dependency>
		<groupId>org.springframework.xd</groupId>
		<artifactId>spring-xd-module-spi</artifactId>
		<version>1.0.4.RELEASE</version>
	</dependency>

	<dependency>
		<groupId>org.springframework.xd</groupId>
		<artifactId>spring-xd-module</artifactId>
		<version>1.0.4.RELEASE</version>
		<scope>test</scope>
	</dependency>	

  </dependencies>
  <!-- <repositories>
  	<repository>
  		<id>spring-milestone</id>
  		<url>http://repo.spring.io/libs-release</url>
  	</repository>
  </repositories> -->
</project>