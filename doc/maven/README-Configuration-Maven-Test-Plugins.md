# Configuration Maven Testing Plugins

List of plugins to facilitate the operations to test with Maven

Step to follow:

* Check Prerequisites
* List of Plugins

## Check Prerequisites

* Verify that the Maven is installed
* Verify that your project have integration with Maven


## List of Plugins

Note : Add to the plugins area <plugins> or in a specific way to the established profile.

- [maven-surefire-plugin](#maven-surefire-plugin)
- [maven-failsafe-plugin](#maven-failsafe-plugin)
- [jacoco-maven-plugin](#jacoco-maven-plugin)





### <a name="maven-surefire-plugin">maven-surefire-plugin</a>

Plugin used to run unit tests

https://maven.apache.org/surefire/maven-surefire-plugin/

```bash
<properties>
	...
	<skip.unit.tests>false</skip.unit.tests>
    ...
</properties>

<profiles>
	...
	<profile>
		<id>dev</id>
		<properties>
			...
			<skip.unit.tests>false</skip.unit.tests>
			..
		</properties>
	</profile>
	...
</profiles>

<plugins>
	...
	<plugin>
		<artifactId>maven-surefire-plugin</artifactId>
		<configuration>
			<skipTests>${skip.unit.tests}</skipTests>
			<excludes>
				<exclude>**/*IntegrationTest</exclude>
				<exclude>**/*IT</exclude>
			</excludes>
			<excludedGroups>com.acme.greeting.api.restful.full.build.integration</excludedGroups>
			<testFailureIgnore>true</testFailureIgnore>
		</configuration>
	</plugin>
	...
</plugins>
```

Your properties can be configured

A good approach can be to configure it by environment

Use Spring Boot Version

Note : Core Plugins

* Execute test
* Generate report/surefire-reports
* Integration with normal test executions

List of Goals
* Goal "surefire:help" : Display help information
* Goal "surefire:test" : Run tests using Surefire





### <a name="maven-failsafe-plugin">maven-failsafe-plugin</a>

Plugin used to run integration tests

https://maven.apache.org/surefire/maven-failsafe-plugin/

```bash
<properties>
	...
	<skip.integration.tests>true</skip.integration.tests>
    ...
</properties>

<profiles>
	...
	<profile>
		<id>dev</id>
		<properties>
			...
			<skip.integration.tests>true</skip.integration.tests>
			..
		</properties>
	</profile>
	...
</profiles>

<plugins>
	...
	<plugin>
		<artifactId>maven-failsafe-plugin</artifactId>
		<configuration>
			<skipITs>${skip.integration.tests}</skipITs>
			<includes>
				<include>**/*RestIT</include>
				<include>**/*RestITCase</include>
				<include>**/*RestClient</include>
			</includes>
		</configuration>
		<executions>
			<execution>
				<goals>
					<goal>integration-test</goal>
					<goal>verify</goal>
				</goals>
			</execution>
		</executions>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version

* Execute test
* Generate report/surefire-reports
* Integration with normal test executions
* ...

List of Goals
* Goal "help" : Display help information on maven-failsafe-plugin
* Goal "integration-test" : Run integration tests using Surefire
* Goal "verify" : Verify integration tests ran using Surefire

```bash
mvn failsafe:verify
```




### <a name="jacoco-maven-plugin">jacoco-maven-plugin</a>

Plugin used to work with Spring Boot application

https://github.com/sidohaakma/semver-maven-plugin

```bash
<plugins>
	...
	<plugin>

	</plugin>
	...
</plugins>
```

Use Spring Boot Version

List of Goals
* XXX
* ...

```bash
mvn spring-boot:run
```





## Authors

* **Víctor Madrid**
