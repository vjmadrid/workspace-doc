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
- [spring-cloud-contract-maven-plugin](#spring-cloud-contract-maven-plugin)





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

Use Spring Boot Version or Normal Version

Note : Core Plugins

* Execute test
* Generate report/surefire-reports
* Integration with normal test executions
* ...

List of Goals
* Goal "help" : Display help information
* Goal "test" : Run tests using Surefire

```bash
mvn surefire:test
```

Running integration test

```bash
<properties>
	...
	<skip.all.tests>false</skip.all.tests>
	<skip.unit.tests>false</skip.unit.tests>
	<skip.integration.tests>false</skip.integration.tests>
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
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-surefire-plugin</artifactId> <!-- surefire plugin version managed by Spring Boot -->
		<configuration>
			<skipTests>${skip.unit.tests}</skipTests>
		</configuration>
		<executions>
			<execution>
				<id>unit-tests</id>
				<phase>test</phase>
				<goals>
					<goal>test</goal>
				</goals>
				<configuration>
					<skipTests>${skip.unit.tests}</skipTests>
					<includes>
						<include>**/*Test.java</include>
					</includes>
				</configuration>
			</execution>
			<execution>
				<id>integration-tests</id>
				<phase>integration-test</phase>
				<goals>
					<goal>test</goal>
				</goals>
				<configuration>
					<skipTests>${skip.integration.tests}</skipTests>
					<includes>
						<include>**/*IT.*</include>
					</includes>
				</configuration>
			</execution>
		</executions>
	</plugin>
	...
</plugins>
```





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

Plugin used to generate code coverage

https://www.eclemma.org/jacoco/trunk/doc/maven.html

```bash
<properties>
	...
	<start-class>com.acme.xxx.yyy.zzzl.Application</start-class>
    ...
</properties>

<plugins>
	...
	<plugin>
				<groupId>org.jacoco</groupId>
				<artifactId>jacoco-maven-plugin</artifactId>
				<version>X.Y.Z</version>
				<executions>

					<execution>
						<id>coverage-initialize</id>
						<goals>
							<goal>prepare-agent</goal>
						</goals>
					</execution>
					<execution>
						<id>coverage-report</id>
						<phase>test</phase>
						<goals>
							<goal>report</goal>
						</goals>
						<configuration>
							<outputDirectory>target/jacoco-report</outputDirectory>
						</configuration>
					</execution>
					
					<execution>
						<id>coverage-check</id>
						<goals>
							<goal>check</goal>
						</goals>
						<configuration>
							<rules>
								<rule>
									<element>CLASS</element>
									<excludes>
										<exclude>${start-class}</exclude>
									</excludes>
									<limits>
										<limit>
											<counter>LINE</counter>
											<value>COVEREDRATIO</value>
											<minimum>80%</minimum>
										</limit>
									</limits>
								</rule>
							</rules>
						</configuration>
					</execution>
				</executions>
			</plugin>
	...
</plugins>
```

Use Spring Boot Version

* Create report : target/site/jacoco/index.html
* Create Check with diferent configuration
* ...

List of Goals
* Goal "help" 
* Goal "prepare-agent"
* Goal "prepare-agent-integration"
* Goal "merge"
* Goal "report"
* Goal "report-integration"
* Goal "report-aggregate"
* Goal "check"
* Goal "dump"
* Goal "instrument"
* Goal "restore-instrumented-classes"

```bash
mvn test
```





### <a name="spring-cloud-contract-maven-plugin">spring-cloud-contract-maven-plugin</a>

Plugin used to test CDC (Consumer Driven Contract)

https://cloud.spring.io/spring-cloud-contract/spring-cloud-contract-maven-plugin/

For JUnit require 

1. Add Test Dependency

```bash
<properties>
	...
	<cdc.spring.cloud.contract.maven.plugin>2.1.1.RELEASE</cdc.spring.cloud.contract.maven.plugin>
    ...
</properties>

<dependency>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-starter-contract-verifier</artifactId>
	<version>${cdc.spring.cloud.contract.maven.plugin}</version>
	<scope>test</scope>
</dependency>
```

2. Add Maven Plugin

```bash
<properties>
	...
	<cdc.spring.cloud.contract.maven.plugin>2.1.1.RELEASE</cdc.spring.cloud.contract.maven.plugin>
    ...
</properties>

<plugin>
	<groupId>org.springframework.cloud</groupId>
	<artifactId>spring-cloud-contract-maven-plugin</artifactId>
	<version>${cdc.spring.cloud.contract.maven.plugin}</version>
	<extensions>true</extensions>
	<configuration>
		<baseClassForTests>
			com.baeldung.spring.cloud.springcloudcontractproducer.BaseTestClass
		</baseClassForTests>
	</configuration>
</plugin>

```

Use Spring Boot Version

* Create report : xxx
* ...

List of Goals
* Goal "help" 
* Goal ...

```bash
mvn test
```





## Authors

* **Víctor Madrid**
