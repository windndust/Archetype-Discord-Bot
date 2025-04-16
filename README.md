### Instructions to use archetype ###
* Clone repo to local environment
* To install archetype project into your local maven repository and archetype catalog, run:

```
mvn install
```


### Command with placeholders to generate project: ###
```
mvn archetype:generate -DarchetypeGroupId=org.mneidinger.maven.archetype -DarchetypeArtifactId=Archetype-Discord-Bot -DarchetypeVersion=0.0.1-SNAPSHOT \
-DgroupId=[insert groupId] -DartifactId=[insert artifactId] -Dversion=[insert version] \
-Dgoals=compiler.compile<br/>
```
* The "operand" `archetype:generate` references the `archetype` plugin and executes the `generate` goal which uses the archetype project to generate a maven project
* The rest of the first line specifies the archetype project to use and has to key into an entry in the archetype-catalog.xml
* Second line specifies the information of your project
* Third line will compile the new project after creating it. It's optional and not necessary to create projects from an archetype

### Example Command to generate project: ###
```
mvn archetype:generate -DarchetypeGroupId=org.mneidinger.maven.archetype -DarchetypeArtifactId=Archetype-Discord-Bot -DarchetypeVersion=0.0.1-SNAPSHOT \
-DgroupId=org.mneidinger.discordbot -DartifactId=DiscordBot -Dversion=0.0.1-SNAPSHOT \
-Dgoals=compiler:compile
```

### Notes ###

This archetype project forces the entered artifactId to all lowercase when injecting into the created project's pom.xml<br/>
It does leave the artifactId unmanipulated when injecting the value into the name element of the pom.xml
https://github.com/windndust/Archetype-Discord-Bot/blob/77cc72c0da14c23186ff2b2c389af353a98b420a/src/main/resources/archetype-resources/pom.xml#L6-L11