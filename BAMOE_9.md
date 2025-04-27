# IBM BAMOE 9 notes

### Creating a brand new project using maven
```
    mvn io.quarkus:quarkus-maven-plugin:2.16.7.Final:create \
    -DprojectGroupId=com.ibm.sample \
    -DprojectArtifactId=quick-kogito \
    -DprojectVersion=1.0.0-SNAPSHOT \
    -DplatformVersion=2.16.7.Final \
    -Dextensions=kogito-quarkus,dmn,resteasy-reactive-jackson,quarkus-smallrye-openapi,quarkus-smallrye-health,quarkus-swagger-ui
```
You may run into a following error
```
[ERROR] Failed to execute goal io.quarkus:quarkus-maven-plugin:2.16.7.Final:create
 (default-cli) on project standalone-pom: Execution default-cli 
 of goal io.quarkus:quarkus-maven-plugin:2.16.7.Final:create 
 failed: A required class was missing while executing 
 io.quarkus:quarkus-maven-plugin:2.16.7.Final:create: 
 org/eclipse/aether/connector/basic/BasicRepositoryConnectorFactory
```
mvn version is important.  Use maven version of 3.8.x (either 3.8.7 and 3.8.4)

If you want to use swagger in production mode still, then add the following  
```
quarkus.swagger-ui.always-include=true
```

If you run into an issue dealing with docker when running mvn quarkus:dev
```
Caused by: java.lang.IllegalStateException: Previous attempts to find a Docker environment failed. Will not retry. Please see logs and check configuration
	at org.testcontainers.dockerclient.DockerClientProviderStrategy.getFirstValidStrategy(DockerClientProviderStrategy.java:212)
	at org.testcontainers.DockerClientFactory.getOrInitializeStrategy(DockerClientFactory.java:150)
```
then run the following instead, just to get by.  
```
 mvn quarkus:dev -Dquarkus.devservices.enabled=false
```

# Resources
IBM BAMOE doc https://github.com/IBM/bamoe-docs.git  
Dev Service https://quarkus.io/guides/dev-services  
Kie Sandbox https://sandbox.kie.org/#/  
Kogito doc [https://docs.kogito.kie.org](https://docs.kogito.kie.org/latest/html_single/#proc-kogito-creating-project_kogito-creating-running)

## BAMOE specific info
https://www.ibm.com/docs/en/ibamoe/9.2.x?topic=installing-bamoe-maven-repository  
https://quay.io/repository/bamoe/maven-repository?tab=tags&tag=9.2.0-ibm-0004  
https://www.ibm.com/docs/en/ibamoe/9.2.x?topic=scenarios-decisions-rules-services-spring-boot  
https://community.ibm.com/community/user/question/understanding-bamoe-dmoe-and-pamoe-differences-and-uses  

## BAMOE pom.xml example
https://github.com/IBM/bamoe-docs/blob/9.2.0/_code/docs/spring-boot/decisions/pom.xml