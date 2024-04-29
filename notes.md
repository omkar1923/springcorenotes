# Springs

**Types:**
1. Spring core / Spring IOC
2. Spring MVC
3. Spring Boot
4. Spring Security

Springs is an open source, widely used, lightweight framework used for developing enterprise Java applications. It is a dedicated framework for Java which can be used to develop both monolithic applications and server-side applications. An application that contains both frontend logic and backend logic is called a monolithic app.

The monolithic architecture is recommended when the application does not demand high server strength. When the application demands high server strength, it is recommended to follow a "Client-Server Architecture". In Client-Server Architecture, the client-side application and server-side applications are developed as two different and independent applications which can be deployed separately. We can say Spring is a framework of frameworks because it supports other frameworks like Hibernate, EJB (Enterprise Java Beans), and many more.

**FEATURES OF SPRING**

There are two key features of the Spring framework:

1. IOC (Inversion of Control)
2. Dependency Injection

**IOC (Inversion of Control):**

In the Spring framework, the programmer is not responsible for creating the objects. The component called the Spring Containers / IOC Containers, which is present inside the Spring framework, will be responsible for creating the required objects and managing the lifecycle of created objects. As the programmer does not have control over object creation, hence the feature is called the inversion of controller. The tasks performed by IOC containers are:

1. To instantiate the application class
2. To configure the object
3. To assemble dependencies between the objects

In Spring framework, the objects are called "Beans". To create an object for us, the IOC container needs some information. We provide that configuration using:

1. XML file (XML-based configuration)
2. Annotations (annotations-based configuration)

**Architecture of Spring IOC container:**

![Spring IOC Container Architecture](link_to_image)

**Note:** 
**POJO and BEAN Class**

| POJO | Bean |
| ---- | ---- |
| POJO can have other private fields, i.e., they can be public, protected, private, and default | Java beans can have only private fields |
| POJO may have/may not have a constructor | Java Beans should have a no-argument constructor |
| All POJOs are not Java beans | All Java beans are POJOs |

**Types of IOC Controller:**

1. BeanFactory (base)
2. ApplicationContext (advanced)


The BeanFactory is the actual container that instantiates, configures, and manages the number of beans. These beans typically collaborate with one another & have dependencies themselves.

**ApplicationContext:**

The application context is Spring's advanced container. Similar to BeanFactory, it can load bean definitions, wire beans together, and dispense beans upon request. The container gets its instructions on what objects to instantiate, configure, and assemble by reading configuration metadata.

**Differences between BeanFactory and ApplicationContext:**
- BeanFactory is an interface. BeanFactory supports lazy loading. BeanFactory doesn't support annotation-based configuration.
- ApplicationContext is an interface. ApplicationContext supports early loading. ApplicationContext supports annotation-based configuration.

**DEPENDENCY INJECTION:**

If a class depends upon another class for its object creation, then such a class is called a dependent class. The class on which it is dependent will be called a "dependency class". As in Spring, the programmer does not create beans (objects), the Spring container itself has to create the object of the dependency class and inject it into the object of the dependent class. This feature of Spring is known as "dependency Injection".

**Ways to do dependency injection:**

1. By using setters (setter injection/getter injection/property injection):
   - We can inject the dependency using a setter method. For setter injection, we need to declare a setter method for each property of a specific class. The `<property>` of `<bean>` is used for setter injection. Inside the respective bean tag, we have to declare a property sub-element. We can pass a value to the properties by providing its variable name to the 'name' attribute and the data which is going to be assigned to the 'value' attribute. By using setters, we can inject dependent objects also where we will use the "ref" attribute instead of the "value" attribute.

   Example:
   ```xml
   <bean class="springs_xml.Student" id="stud">
       <property name="name" value="Vibhas"></property>
       <property name="age" value="23"></property>
   </bean>
<bean class="spring_hibernate_xml.dto.PanCard" id="card">
    <constructor-arg name="id" value="1"></constructor-arg>
    <constructor-arg name="name" value="Vibhas"></constructor-arg>
    <constructor-arg name="address" value="Amravati">
    </constructor-arg>
</bean>

<bean class="spring_hibernate_xml.dto.Person" id="person">
    <constructor-arg name="id" value="1"></constructor-arg>
    <constructor-arg name="name" value="Vibhas"></constructor-arg>
    <constructor-arg name="phone" value="7887905972">
    </constructor-arg>
    <constructor-arg name="address" value="Amravati">
    </constructor-arg>
    <constructor-arg name="card" ref="card"></constructor-arg>
</bean>
