SpringBoot
---
[Thank you Dan Vega](https://www.youtube.com/watch?v=UgX5lgv4uVM&t=4377s) \
[Documentation for Springboot](https://docs.spring.io/spring-framework/reference/)

### Starting a Spring Boot project
Go to [Spring Initializr](start.spring.io) to quickly set up a Spring Boot project

Some terms:
- Project: Builder for project
- Language: Programming language supported
- Spring Boot: Version, usually just use the default
- Project Metadata:
  - Group: Default package, domain in reverse order (com.google)
  - Artifact: Thing thats being built
  - Name: Same as above, I guess
  - Description: What is the application (content calendar REST API)
  - Package name: autogenerated name for package
  - Packaging: jar: runs on pc, war: runs on web
  - Java: java version
- Dependencies: Generic needs of project families
  - Spring web includes: Spring MVC, Apache Tomcat, etc.

Once filled out, click the `Generate` button. It will download a zip file that can be unzipped to show the framework.

### Understanding the Spring Boot Project

#### Spring Boot Core Concepts
- @Component: basic class level annotation to create a singleton global instance. Bean name is class name
- @Bean: basic method level annotation to create a global instance. Bean name is method name.
    - Bean methods can only be run in classes tagged with @configuration
```
public class Application {
    public static void main(String[] args){
        ConfigurableApplicationContext context = SpringApplication.run(Application.class, args);
        context.getBean("restTemplate");
    }
}

@Configuration
public class ExampleClass {

    @Bean
    public RestTemplate restTemplate(){
        return new RestTemplateBuilder().build();
    }
}
```

- If we want to list all the beans in an application, we can also do \
 `Arrays.stream(context.getBeanDefinitionNames()).foreach(System.out::println)`

#### Folder Structure:
- .idea : For intellij idea
- .mvn : maven wrapper that allows the program to run without user installing maven
-  src : where all the logic is stored for the project
- .gitignore : prepopulated to ignore some maven stuff
- HELP.md :  Help file
- mvnw : maven stuff
- mvnw.cmd : more maven stuff
- pom.xml : list dependencies etc

#### src folder
Within the src folder there are other folders
- main : Execution for project
    - java > com.example.package (main package)
        - **Application: Houses `public static void main`, the main function.
        - Try crete everything here, sub packages, classes, etc.

#### pom.xml
Here are some terms to know in the pom.xml
- It defines the project metadata, and version of the project.
- It lists the java version being used
- It lists the dependencies to pull and use
  - We may see artifactID's: something-something-starter. These are links to other xml files that's needed for the dependency above.

#### Using Java's record class
```
public record Content (
    Integer id,
    String title,
    Yoruclass myclass
){}
```
Will create an  immutable class that auto fills the:
-  constructor (can still overload and define)
    -  Defining default
```
public Content{
   Objects.requireNonNull(id),
   Objects.requireNonNull(title),
   Objects.requireNonNull(myclass)
}
```
    - Overloading  

    
-  getter
-  equals (everything must match for it to be equal)
-  tostring (returns everything as a string e.g. Class[id=id, title=name\] 