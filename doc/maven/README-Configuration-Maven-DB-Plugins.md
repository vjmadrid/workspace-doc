# Configuration Maven DB Plugins

List of plugins to facilitate the operations in Database with Maven

Step to follow:

* Check Prerequisites
* List of Plugins

## Check Prerequisites

* Verify that the Maven is installed
* Verify that your project have integration with Maven


## List of Plugins

Note : Add to the plugins area <plugins> or in a specific way to the established profile.

- [liquibase-maven-plugin](#liquibase-maven-plugin)


### <a name="liquibase-maven-plugin">liquibase-maven-plugin</a>

Plugin used to control to Liquibase 

https://www.liquibase.org/documentation/maven/index.html

https://www.liquibase.org/documentation/maven/generated/update-mojo.html

https://www.liquibase.org/documentation/spring.html

```bash
<plugins>
	...
	<plugin>
		<groupId>org.liquibase</groupId>
		<artifactId>liquibase-maven-plugin</artifactId>
		<version>${liquibase.maven.plugin.version}</version>

		<configuration>
			<propertyFile>src/main/resources/liquibase.properties</propertyFile>
		</configuration>
		
	</plugin>
	...
</plugins>
```

Use Spring Boot Version

List of Goals
* liquibase:changelogSync
* liquibase:changelogSyncSQL
* liquibase:clearCheckSums
* liquibase:dbDoc
* liquibase:diff
* liquibase:dropAll
* liquibase:generateChangeLog
* liquibase:help
* liquibase:listLocks
* liquibase:releaseLocks
* liquibase:rollback
* liquibase:rollbackSQL
* liquibase:status
* liquibase:tag
* liquibase:update
* liquibase:updateSQL
* liquibase:updateTestingRollback
* liquibase:futureRollbackSQL
* liquibase:migrate DEPRECATED use update instead
* liquibase:migrateSQL DEPRECATED use updateSQL instead
* ...

```bash
mvn liquibase:update
```





## Authors

* **Víctor Madrid**
