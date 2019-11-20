# Configuration Maven Build Plugins

List of plugins to facilitate the operations to carry out with Maven

Step to follow:

* Check Prerequisites
* List of Plugins

## Check Prerequisites

* Verify that the Maven is installed
* Verify that your project have integration with Maven


## List of Plugins

Note : Add to the plugins area <plugins> or in a specific way to the established profile.

- [spring-boot-maven-plugin](#spring-boot-maven-plugin)
- [maven-clean-plugin](#maven-clean-plugin)
- [maven-resources-plugin](#maven-resources-plugin)
- [maven-compiler-plugin](#maven-compiler-plugin)
- [maven-verifier-plugin](#maven-verifier-plugin)
- [build-helper-maven-plugin](#build-helper-maven-plugin)
- [build-helper-maven-plugin](#build-helper-maven-plugin)




### <a name="spring-boot-maven-plugin">spring-boot-maven-plugin</a>

Plugin used to work with Spring Boot application

https://docs.spring.io/spring-boot/docs/current/maven-plugin/usage.html

```bash
<plugins>
	...
	<plugin>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-maven-plugin</artifactId>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version


List of Goals
* Goal "run" : Execute Spring Boot application
* Goal "repackage" : Create Jar / War auto-executable
* Goal "build-info" : Generate a build information that can be used by the Actuator
* ...

```bash
mvn spring-boot:run
```





### <a name="maven-clean-plugin">maven-clean-plugin</a>

Plugin used to clean the project

Use with the comman mvn

https://maven.apache.org/plugins/maven-clean-plugin/

```bash
<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-clean-plugin</artifactId>
        <version>X.Y.Z</version>
		<configuration>
			<filesets>
				<fileset>
					<directory>output-resources</directory>
				</fileset>
			</filesets>
		</configuration>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version or Normal Version

Note : Core Plugins

* Configure resource Encoding : UTF-8
* Copy files from a input resource directory to a output directory
	* Goal "clean" : cleans the build
	* Goal "help" : help information


Running during a build

```bash
<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-clean-plugin</artifactId>
        <version>X.Y.Z</version>
		<executions>
			<execution>
				<id>auto-clean</id>
				<phase>initialize</phase>
				<goals>
					<goal>clean</goal>
				</goals>
			</execution>
        </executions>
	</plugin>
	...
</plugins>
```

```bash
mvn clean:clean
or
mvn clean
```





### <a name="maven-resources-plugin">maven-resources-plugin</a>

Plugin used to handle the project resources

https://maven.apache.org/plugins/maven-resources-plugin/

```bash
<properties>
	...
	<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    ...
</properties>

<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-resources-plugin</artifactId>
		<version>X.Y.Z</version>
		<configuration>
			<encoding>${project.build.sourceEncoding}</encoding>
		</configuration>
	</plugin>
	...
</plugins>
```

Use Spring Boot Version or Normal Version

Note : Core Plugins

* Configure resource Encoding : UTF-8
* Copy files from a input resource directory to a output directory
	* Goal "resources" : copy resources for main source code
	* Goal "testResources" : copy resources for test source code
	* Goal "copy-resources" : copy resources for arbitrary source code
* Replace placeholder variables in the resource file
* ...





### <a name="maven-compiler-plugin">maven-compiler-plugin</a>

Plugin used to compile the project source

https://maven.apache.org/plugins/maven-compiler-plugin/

```bash
<properties>
	...
	<java.version>1.8</java.version>
	<project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
    ...
</properties>

<plugins>
	...
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-compiler-plugin</artifactId>
		<version>X.Y.Z</version>
		<configuration>
			<source>${java.version}</source>
			<target>${java.version}</target>
			<encoding>${project.build.sourceEncoding}</encoding>
		</configuration>
	</plugin>
	...
</plugins>
```


Use Spring Boot Version or Normal Version

Note : Core Plugins

* Configure compilation version : source and target
* Configure encoding
	* Goal "compile" : Compile main source files
	* Goal "testCompile" : Compile test source files
* ...





### <a name="maven-verifier-plugin">maven-verifier-plugin</a>m

Plugin used to verify the existence of files and directories

https://maven.apache.org/plugins/maven-verifier-plugin/

```bash
<properties>
	...
	<verifier.verification.file>src/test/verifier/verifications-test.xml</verifier.verification.file>
    ...
</properties>

<plugins>
	...
	<plugin>
        <artifactId>maven-verifier-plugin</artifactId>
        <version>X.Y.Z</version>
        <configuration>
            <verificationFile>${verifier.verification.file}</verificationFile>
            <failOnError>false</failOnError>
        </configuration>
        <executions>
			<execution>
				<id>main</id>
				<phase>verify</phase>
				<goals>
					<goal>verify</goal>
				</goals>
			</execution>
		</executions>
    </plugin>
	...
</plugins>
```

Use Spring Boot Version or Normal Version

Configuration with a verification File

List of Goals
* Goal "verify" : Verify the existence od files and directories


```bash
mvn verifier:verify
```





### <a name="build-helper-maven-plugin">build-helper-maven-plugin</a>

Plugin used to help with Maven build lifecycle

https://www.mojohaus.org/build-helper-maven-plugin/usage.html

```bash
<plugins>			
	<plugin>
		<groupId>org.codehaus.mojo</groupId>
		<artifactId>build-helper-maven-plugin</artifactId>
		<executions>
			<execution>
				<phase>generate-sources</phase>
				<goals>
					<goal>add-source</goal>
				</goals>
				<configuration>
					<sources>
						<source>src/main/another-src</source>
					</sources>
				</configuration>
			</execution>
			<execution>
				<id>add-integration-test-source</id>
				<phase>generate-test-sources</phase>
				<goals>
					<goal>add-test-source</goal>
				</goals>
				<configuration>
					<sources>
						<source>src/integration-test/java</source>
					</sources>
				</configuration>
			</execution>
			<execution>
				<id>add-integration-test-resource</id>
				<phase>generate-test-resources</phase>
				<goals>
					<goal>add-test-resource</goal>
				</goals>
				<configuration>
					<resources>
						<resource>
							<directory>src/integration-test/resources</directory>
						</resource>
					</resources>
				</configuration>
			</execution>
		</executions>
	</plugin>
</plugins>
```
Use Spring Boot Version

* Add another source directory
* Add another resource directory
* Add another test source directory
* Add another test resource directory
* ...

List of Goals
* Goal "add-source" : Add more source directories to the POM
* Goal "add-test-source" : Add test source directories to the POM
* Goal "add-resource" : Add more resource directories to the POM
* Goal "add-test-resource" : Add test resource directories to the POM
* Goal "attach-artifact" : Attach additional artifacts to be installed and deployed
* Goal "maven-version" : Set a property containing the current version of maven
* Goal "regex-property" : Sets a property by applying a regex replacement rule to a supplied value
* Goal "regex-properties" : Sets a property by applying a regex replacement rule to a supplied value
* Goal "released-version" : Resolve the latest released version of this project
* Goal "parse-version" : Parse the version into different properties
* Goal "remove-project-artifact" : Remove project's artifacts from local repository
* Goal "reserve-network-port" : Reserve a list of random and unused network ports
* Goal "local-ip Retrieve" : current host IP address
* Goal "cpu-count Retrieve" : number of available CPU
* Goal "timestamp-property" : Sets a property based on the current date and time
* Goal "uptodate-property" : Sets a property according to whether a file set's outputs are up to date with respect to its inputs
* Goal "uptodate-properties" : Sets multiple properties according to whether multiple file sets' outputs are up to date with respect to their inputs
* Goal "rootlocation" : Sets a property which defines the root folder of a multi module build


List of Goals
* Goal "enforce" : Execute rules
* Goal "display-info" : Display info detected

```bash
mvn build-helper:add-source
```





### <a name="maven-enforcer-plugin">maven-enforcer-plugin</a>

Plugin used to help with the environmental constrains : JDV, Maven Version, Environment var, rules, ...

https://maven.apache.org/enforcer/maven-enforcer-plugin/

```bash
<plugins>			
	<plugin>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-enforcer-plugin</artifactId>
		<version>X.Y.Z</version>
		<executions>
			<execution>
				<id>enforce</id>
				<goals>
					<goal>enforce</goal>
				</goals>
				<configuration>
					<rules>
						<banDuplicatePomDependencyVersions/>
						<requireMavenVersion>
							<version>3.0</version>
							<message>Invalid Maven version. It should, at least, be 3.0</message>
						</requireMavenVersion>
						<requireJavaVersion>
							<version>1.8</version>
							<message>Invalid Java version. It should, at least, be 1.8 OpenJDK</message>
						</requireJavaVersion>
						<requireActiveProfile>
							<profiles>${spring.profiles.active}</profiles>
							<message>Missing active profiles</message>
							<level>ERROR</level>
						</requireActiveProfile>
					</rules>
				</configuration>
			</execution>
		</executions>
	</plugin>
</plugins>
```
Use Spring Boot Version or Normal Version

* Add differents constraints
* ...

List of Goals
* Goal "enforce" : Execute rules
* Goal "display-info" : Display info detected

```bash
mvn enforcer:enforce
```





## Authors

* **Víctor Madrid**
