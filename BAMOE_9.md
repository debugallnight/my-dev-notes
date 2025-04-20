# IBM BAMOE 9 notes

- mvn version is important.  Don't forget to use 3.8.7 

## Working copy.  Read the readme file included when running the build.
```
    mvn io.quarkus:quarkus-maven-plugin:2.16.7.Final:create \
    -DprojectGroupId=com.ibm.sample \
    -DprojectArtifactId=quick-kogito \
    -DprojectVersion=1.0.0-SNAPSHOT \
    -DplatformVersion=2.16.7.Final \
    -Dextensions=kogito-quarkus,dmn,resteasy-reactive-jackson,quarkus-smallrye-openapi,quarkus-smallrye-health,quarkus-swagger-ui
```