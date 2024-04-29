# Springs

## Types:
1. Spring Core / Spring IOC
2. Spring MVC
3. Spring Boot
4. Spring Security

- Springs is an open-source, widely used, lightweight framework for developing enterprise Java applications.
- It's suitable for both monolithic and server-side applications.
- A monolithic application integrates both frontend and backend logic.

## Features of Spring:

1. **IOC (Inversion of Control):**
   - In Spring, the framework creates and manages objects (Beans) instead of the programmer.
   - IOC containers handle object creation, configuration, and dependency assembly.
   - Configuration can be done using XML files or annotations.

2. **Dependency Injection:**
   - Dependency Injection is a feature where Spring container injects dependencies into dependent classes.
   - It can be done via setters (setter injection) or constructors (constructor injection).

## IOC Container Types:

1. **BeanFactory (base):**
   - Provides basic IOC functionality.
   - Supports lazy loading.

2. **ApplicationContext (advanced):**
   - Offers advanced features.
   - Supports early loading.
   - Supports annotation-based configuration.

## Dependency Injection Methods:

1. **Setter Injection:**
   - Dependencies are injected using setter methods.
   - Configuration is done using `<property>` tags in XML or annotations.

2. **Constructor Injection:**
   - Dependencies are injected via constructor arguments.
   - Configuration is done using `<constructor-arg>` tags in XML.
