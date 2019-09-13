# File System Configuration Server 
Spring Boot Configuration Server to access all the Configuration.

This Server will be able to read all the configuration from a specified location and serve to all the applications asking for Configuration by the their Spring Application Name. 

The FileName should match the Spring Application Name in order to find the right configuration.

The Properties that are mentioned in the Application.yml or Application.properties file are available to all applications which helps with avoiding duplication 

The server itself is a Spring Boot App which can be run as like any other App.

## Configuring the Path to read from  Configuration 

```
spring.cloud.config.server.native.searchLocations=  # Path to the Config Folder

```

## Configuring  Spring Boot Applications to read Configuration from the Server 

### Dependencies needed

```
<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-config</artifactId>
</dependency>

<dependencyManagement>
	<dependencies>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-dependencies</artifactId>
			<version>Finchley.RELEASE</version>
			<type>pom</type>
			<scope>import</scope>
		</dependency>
	</dependencies>
</dependencyManagement>

```

### Bootstrap Properties Needed (bootstrap.properties)

#### Be Sure to give a Unique Name to your Application 

The config server uses your Application Name to look up and server your configuration

```
spring.application.name=Unique Application Name
```

```
spring.cloud.config.uri= http://localhost:9001 # Url to the Configuration Server 

management.security.enabled=false

```

### Add the Appropriate Properties/ Yaml File of your Spring Application to the Config Folder

### Resources 

https://cloud.spring.io/spring-cloud-config/multi/multi__spring_cloud_config_server.html
 
