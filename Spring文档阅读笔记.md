# Spring官方文档阅读笔记

## Spring Boot Reference Documents

 - version 2.4.4

### Using Spring Boot

#### 1. Build Systems
#### 2. Structuring Your Code
#### 8. Developer Tools

Maven 

```xml
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-devtools</artifactId>
        <optional>true</optional>
    </dependency>
</dependencies>
```

note
```properties
spring.devtools.restart.enabled=true
```

tips

>Flagging the dependency as optional in Maven or using the developmentOnly configuration in Gradle (as shown above) prevents devtools from being transitively applied to other modules that use your project.   

>Repackaged archives do not contain devtools by default. If you want to use a certain remote devtools feature, you need to include it. When using the Maven plugin, set the excludeDevtools property to false. When using the Gradle plugin, configure the task’s classpath to include the developmentOnly configuration.

##### 8.1 Propety Defaults

note

>If you don’t want property defaults to be applied you can set spring.devtools.add-properties to false in your application.properties

tips

>For a complete list of the properties that are applied by the devtools, see [DevToolsPropertyDefaultsPostProcessor](https://github.com/spring-projects/spring-boot/blob/v2.4.4/spring-boot-project/spring-boot-devtools/src/main/java/org/springframework/boot/devtools/env/DevToolsPropertyDefaultsPostProcessor.java).

##### 8.2 Automatic Restart

1. triggering a restart 

>in IntelliJ IDEA, `Build + button`  
>in maven,running `mvn complie `

note

>If you are restarting with Maven or Gradle using the build plugin you must leave the forking set to enabled. If you disable forking, the isolated application classloader used by devtools will not be created and restarts will not operate properly.

