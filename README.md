
## Clone

Clone the GitHub repository to your computer.

## Install JAR

Place the JAR file in the local Git repository by letting Maven perform an install:

```shell 
mvn install:install-file
 -DgroupId=[group-id]
 -DartifactId=[artifact-id]
 -Dversion=[version]
 -Dpackaging=jar
 -Dfile=[path-to-file]
 -DlocalRepositoryPath=[path-to-git-repo]
 -DgeneratePom=true 
 -DcreateChecksum=true 
 -DpomFile=pom.xml  
```

- [group-id], [artifact-id], [version] and [packaging-format] define the Maven properties of the file to install.
- [path-to-file] is the path to the JAR file to install.
- [path-to-git-repo] is the path to the local Git repository on your computer.

After successful execution of the command a folder structure is created in the local Git repository. This structure and the files in it make it usable as a Maven repo.

## Commit & Publish
Commit the changes, that were made by executing the Maven install command, to the local Git repository.

Publish the updated repository to GitHub. The JAR file is now ready to be used in a Maven POM file.

## Use
Add the GitHub repository to the POM file of the project:

```xml
<repository>
    <id>git-47billion</id>
    <name>47billion's Git based repo</name>
    <url>https://github.com/47billion/maven-repo/raw/master/</url>
</repository>
```

If the POM file does not include a definition of repositories, put the XML above inside a <repositories> element. Declare the dependency in the POM as you do for every dependency.

That's it! Maven should now be able to use the JAR file.
