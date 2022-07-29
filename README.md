Jakarta EE 9/9.1 Sample App
=========================

The app is for testing the New Relic Java Agent for Jakarta EE 9/9.1

## Build

`./gradlew build`

OR

`mvn install`

NOTE:  Jakarta 9.1 specific version of code in `jee91` branch and requires Java 11 to build and run.


## Tomcat 10.x

Add a `setenv.sh` (if does not exist) to the `$TOMCAT_HOME/bin` directory with the follow line:

`export CATALINA_OPTS="$CATALINA_OPTS -javaagent:/location/to/newrelic.jar -Dnewrelic.config.file=/location/to/newrelic.yml -Dnewrelic.environment=[production|staging]"`

Copy the war file from `build/libs` (or `target`) into `$TOMCAT_HOME\webapps`

Then run `$TOMCAT_HOME\bin\startup.sh`


## Run Test Requests

The project uses HTTPie https://httpie.io/ but the `spam-hello.sh` could easily be changed to use `curl` instead.