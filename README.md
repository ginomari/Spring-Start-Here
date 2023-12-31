# Spring Start Here

wip

## Topics

**Chapter 2** - Introduction to Spring Context
- A place in memory of the app which we add all the object instances and establish relationships that the framework will manage.
- ```@Configuration``` class, a special class used to instruct Spring to do specific actions. i.e. adding beans.
- Adding instances called *"beans"* to the Spring Context in three different ways:
    - Method-level ```@Bean``` annotation inside the ```@Configuration``` class;
    - Class-level ```@Component``` and ```@ComponentScan``` stereotype annotations;
    - and ```registerBeans()``` method.
- Bean lifecycle and JSR-250 Common Annotations:
    - ```@PostConstruct```, instructs Spring to call that method after the constructor finishes its execution.
    - ```@PreDestroy```, signal that the instance is in the process of being removed by the container.
- ```getBean()``` method to retrieve instances inside the Spring Context.


**Chapter 3** - Wiring Beans
- Establish relationships among beans in the Spring context.
- Three ways to establish bean relationships:
    - Directly refer to the ```@Bean``` annotated method.
    - Define a parameter in the ```@Bean``` method.
    - Use ```@Autowired``` annotation on fields, constructors, or setters.
- Spring uses *Dependency Injection* (DI) to provide values or references.
- Avoid *circular dependencies* between beans.
- Resolve conflicts when multiple beans of the same type exist:
    - Use ```@Primary``` annotation for default injection.
    - Use ```@Qualifier``` annotation with named beans.
 

**Chapter 4** - Using Abstractions
- Continuation of Dependency Injection (DI) in Chapter 3.
- Sample of actual implementations on real world applications.
- Using interfaces to define contracts.
- Decoupling implementations through abstractions based on structural patterns.
- Introduction to meta-annotations of ```@Component```:
    - Use ```@Service``` annotation for service layer.
    - Use ```@Repository``` annotation for persistence layer.

**Chapter 5** - Bean Scopes and Life Cycle
- Definition of a Bean
- The scope of beans defines how the framework manages the object instances.
- Two bean scopes: singleton and prototype.
	- With Singleton ```@Scope(BeanDefinition.SINGLETON)```, each instance has a unique name, and using that name you always refer to that specific instance.
	- With Prototype ```@Scope(BeanDefinition.PROTOTYPE)```, each type hs a unique name associated with it. Spring creates new instace of that type everytime you refer to the bean name.
- Advantages and disadvantages of both scopes.
- Configure singleton bean initialization in context through ```@lazy``` and ```@eager``` annotations. By default, a bean is eagerly instantiated
- Injecting a prototype-scoped bean into a singleton-scoped bean where a singleton instance always uses the same prototype instance, which spring injects when it creates the singleton instance.
