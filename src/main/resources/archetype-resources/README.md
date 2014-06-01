Overview
========

This project is a basic protocol buffer Java project. It provides a location 
for .proto files and adds maven settings to generate the Proto Java files on 
each build.

* src/main/proto = Location for .proto files
* target/generated-sources = Location of Proto Java files

Eclipse integration
-------------------

This archetype comes preconfigured for eclipse integration. This has some 
side-affects, namely that the maven-antrun-plugin runs on every incremental 
build. This might become costly in a large project so you may need to modify or
remove the lifecycle mapping:

```xml
<pluginExecution>
	<pluginExecutionFilter>
		<groupId>org.apache.maven.plugins</groupId>
		<artifactId>maven-antrun-plugin</artifactId>
		<versionRange>1.3</versionRange>
		<goals>
			<goal>run</goal>
		</goals>
	</pluginExecutionFilter>
	<action>
		<execute>
			<runOnIncremental>true</runOnIncremental>
		</execute>
	</action>
</pluginExecution>
```

You may need to enable the project refresh to see the new files immediately.
This setting is located under Window > Preferences > Workspace > and check
"Refresh using native hooks or polling".