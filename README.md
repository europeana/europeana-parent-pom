# Europeana Parent POM

The Europeana Parent POM is a Maven POM that can be used as a starting point for Europeana projects that use Maven.
The pom contains common versions of used libraries as well as commonly-used Maven plugins and build steps.

Since the Europeana Parent POM is stored on Europeana's Artifactory any Maven project that uses the Europeana parent POM
should add the Europeana Artifactory as a repository in either the project's POM or in the user's Maven settings.xml. 
The latter is of course a more elegant solution.

You can use the settings.xml file that is present in this project as an example and copy it to your local .m2 folder to
get things up and running quickly. Make sure you don't forget to define the Europeana pom as your pom's parent, for 
example:

    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    	<modelVersion>4.0.0</modelVersion>
        <parent>
            <artifactId>europeana-parent-pom</artifactId>
            <groupId>eu.europeana</groupId>
            <version>1.5</version>
        </parent>
    	<groupId>eu.europeana</groupId>
    	<artifactId>myNewProject</artifactId>
    	....
