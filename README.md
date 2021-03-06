How to build
============

*Starting with development of version 4.0, Hibernate uses Gradle (http://gradle.org) as its build tool.*

This README describes some of the basics developers and contributors new to Gradle need to know to get productive quickly.

Resources
---------

To start with - here is a list of resources to obtain more information about Gradle:

* The Gradle User Guide : http://gradle.org/docs/current/userguide/userguide_single.html
* Gradle DSL Guide : http://gradle.org/docs/current/dsl/index.html
* Additional Hibernate/Gradle information : http://community.jboss.org/wiki/GradleFAQ

Here is the link of how to set up ~/.m2/settings.xml to use JBoss Nexus repo.

* JBoss Nexus User Guide : http://community.jboss.org/wiki/MavenGettingStarted-Users

Executing Tasks Across All Modules
----------------------------------

To execute a task across all modules, simply perform that task from the root directory.  Gradle will visit each
subproject and execute that task if the subproject defines it.

Executing Tasks In Specific Module
----------------------------------

To execute a task in a specific module you can either:
1. `cd` into that module directory and execute the task
2. name the "task path".  For example, in order to run the tests for the _hibernate-core_ module from the root directory you could say `gradle hibernate-core:test`

Common Java-module tasks
------------------------

* _build_ - Assembles (jars) and tests this project
* _buildDependents_ - Assembles and tests this project and all projects that depend on it.  So think of running this in hibernnate-entitymanager, Gradle would assemble and test hibernate-entitymanager as well as hibernate-envers (because envers depends on entitymanager)
* _classes_ - Compiles the main classes
* _testClasses_ - Compiles the test classes
* _jar_ - Generates a jar archive with all the compiled classes
* _test_ - Runs the tests
* _uploadArchives_ - Think Maven deploy
* _install_ - Installs the project jar to your local maven cache (aka ~/.m2/repository)
* _eclipse_ - Generates an Eclipse project
* _idea_ - Generates an IntelliJ/IDEA project.
* _clean_ - Cleans the build directory