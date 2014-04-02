# Documentation :: gatling by org.apache.easyant.plugins

# Description

Provides gatling (stress tool) integration. The following repository is required to get gatling dependencies: http://repository.excilys.com/content/groups/public
	
# Example

```xml
<ea:plugin organisation="org.apache.easyant.plugins" module="gatling" revision="0.1"/>
```
Organisation attribute is optional. If not specified default one will be used.

```xml
<ea:plugin module="gatling" revision="0.1"/>
```

## Available targets

|target name|description|extension point|depends|
|-----------|-----------|---------------|-------|
|gatling:init||||
|gatling:execute|run gatling tests||gatling:init|

## Module parameters

### Properties

|property|description|required|default value|
|--------|-----------|--------|-------------|
|gatling.outputDirectoryBaseName|Force the name of the directory generated for the results of the run|false||
|gatling.reportsOnly|Generates the reports for the simulation in this folder|false||
|gatling.requestBodiesFolder|Uses this folder as the folder where request bodies are stored|false|${basedir}/src/test/resources/request-bodies|
|gatling.simulationClass| A name of a Simulation class to run. This takes precedence over the includes / excludes parameters.|false||
|gatling.fork|Forks the execution of Gatling plugin into a separate JVM|false|true|
|gatling.simulationsFolder.includes|Sets the list of include patterns to use in directory scan for simulations. Relative to simulationsFolder|false|**/*|
|gatling.dataFolder|Uses this folder as the folder where feeders are stored|false|${basedir}/src/test/resources/data|
|gatling.simulationsFolder.excludes|Sets the list of exclude patterns to use in directory scan for simulations. Relative to simulationsFolder|false||
|gatling.resultsFolder|Uses this folder as the folder where results are stored|false|${target.reports}/gatling|
|gatling.configDir|Uses this file as the configuration file|false|${basedir}/src/test/resources|
|gatling.newEnvironment|Do not propagate old environment when new environment variables are specified (ignored if fork is disable|false|false|
|target.reports|base directory for reports|false|${target}/reports|
|gatling.simulationsFolder|Uses this folder to discover simulations that could be run|false|${basedir}/src/test/scala|
|gatling.jvmArgs|Extra JVM arguments to pass when running Gatling.|false|-server -XX:+UseThreadPriorities -XX:ThreadPriorityPolicy=42 -Xms512M -Xmx512M -Xmn100M -Xss2M -XX:+HeapDumpOnOutOfMemoryError -XX:+AggressiveOpts -XX:+OptimizeStringConcat -XX:+UseFastAccessorMethods -XX:+UseParNewGC -XX:+UseConcMarkSweepGC -XX:+CMSParallelRemarkEnabled -XX:+CMSClassUnloadingEnabled -XX:CMSInitiatingOccupancyFraction=75 -XX:+UseCMSInitiatingOccupancyOnly -XX:SurvivorRatio=8 -XX:MaxTenuringThreshold=1|
|gatling.noReports|Runs simulation but does not generate reports.|false|false|
|gatling.failOnError|Will cause the project build to look successful, rather than fail, even if there are Gatling test failures. This can be useful on a continuous integration server, if your only option to be able to collect output files, is if the project builds successfully.|false|true|

## Ivy Configurations

|name|description|extends|visibility|deprecated|
|----|-----------|-------|----------|----------|
|default|runtime dependencies artifact can be used with this conf|[]|public||
|test|this scope indicates that the dependency is not required for normal use of the application, and is only available for the test compilation and execution phases.|[]|private||
|provided|this is much like compile, but indicates you expect the JDK or a container to provide it. It is only available on the compilation classpath, and is not transitive.|[]|public||

## Dependencies Overview

|Organisation|Module|Revision|
|------------|------|--------|
|com.typesafe|config|1.2.0|
|com.typesafe|config|1.0.1|
|io.gatling|gatling-app|2.0.0-M3a|

