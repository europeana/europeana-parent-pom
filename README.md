# Europeana Parent POM

The Europeana Parent POM is a Maven POM that is used for common build and release steps for Europeana Java/Maven projects.

## Setup ##
Since the Europeana Parent POM is stored on Europeana's Artifactory any Maven project that uses the Europeana parent POM
should add the Europeana Artifactory as a repository in either the project's POM or in the user's Maven settings.xml. 

You can use the settings.xml file that is present in this project as an example and copy it to your local .m2 folder to
get things up and running quickly. Make sure you don't forget to define the Europeana POM as your pom's parent, for 
example:

    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    	<modelVersion>4.0.0</modelVersion>
        <parent>
            <groupId>eu.europeana</groupId>
            <artifactId>europeana-parent-pom</artifactId>
            <version>2.0</version>
        </parent>
    	<groupId>eu.europeana</groupId>
    	<artifactId>myNewProject</artifactId>
    	....

## Usage ##

The war plugin has been configured to search for a `src/main/resources/build.properties` file and on each build will fill
the maven variable placeholders that the build.properties file contains (see for example 
https://github.com/europeana/api2/blob/develop/api2-war/src/main/resources/build.properties)

Furthermore, the Parent POM has profiles that can be invoked:

The **default** profile will generate a build number.

The **javadoc** profile will generate java doc files

The **release** profile will 
 - check that no snapshot dependencies are present
 - generate a build number
 - generate a sources jar
 - generate java doc files
 - generate a maven site

## Note ##
The 1.x releases of the Parent POM also contains commonly-used dependencies, but since we are moving towards microservices
 and different technologies, all dependencies have been phased out in 2.x releases