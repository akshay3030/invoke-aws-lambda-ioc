#invoke-aws-lambda-ioc
invoke aws lambda using springboot api with inversion of control (Dependency Injection)


#Maven Commands
mvn clean install
mvn spring-boot:run -Drun.profiles=local
java -jar target/<<name>>.jar --spring.profiles.active=local

#Learnings
Dependency Injection(IOC)

Method with return type of interface(you can return any class that implement that interface

@Autowired  : This annotation allows Spring to resolve and inject collaborating beans into your bean or class.

//@Inject is javax.inject.Inject JavaEE5 way of dependency injection :
//@Autowired is spring way of doing it. 

@Profiles :  Spring Profiles provide a way to segregate parts of your application configuration and make it only available in certain environments. Any @Component or @Configuration can be marked with @Profile to limit when it is loaded. Can be implemented at Class(@Configuration,@Component) or Method(@Bean) Level.
http://docs.spring.io/autorepo/docs/spring-boot/current/reference/html/boot-features-profiles.html
https://www.mkyong.com/spring/spring-profiles-example/

@Bean : Indicates that a method produces a bean to be managed by the Spring container.

@Configuration : Indicates that a class declares one or more @Bean methods and may be processed by the Spring container to generate bean definitions and service requests for those beans at runtime

@Service : This annotation serves as a specialization of @Component, allowing for implementation classes to be autodetected through classpath scanning. Implementation of @Component

@Controller : annotation is an annotation used in Spring MVC framework (the component of Spring Framework used to implement Web Application). The @Controller annotation indicates that a particular class serves the role of a controller. The @Controller annotation acts as a stereotype for the annotated class, indicating its role. The dispatcher scans such annotated classes for mapped methods and detects @RequestMapping annotations. This is also an implementation of @Component. t is typically used in combination with annotated handler methods based on the RequestMapping annotation.

@RestController : A convenience annotation that is itself annotated with @Controller and @ResponseBody

@ResponseBody : When you use the @ResponseBody annotation on a method, Spring converts the return value and writes it to the http response automatically. Each method in the Controller class must be annotated with @ResponseBody

# Reading variable from application.properties
@Value("${cloud.aws.profile}")
private String profile;
