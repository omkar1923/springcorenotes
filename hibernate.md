**J2EE Basics:**
- **Pom:** Stands for Project Object Model, a file in Maven projects containing project configuration details.
- **Pojo:** Short for Plain Old Java Objects, simple Java classes without any special annotations or requirements.
- **Static Context:**
  - Accessing static elements within the same class can be done directly.
  - Accessing static elements from a different class requires using the class name.
- **Non-Static Context:**
  - Accessing non-static elements within the same class can be done directly.
  - Accessing non-static elements from a different class requires using the class name.

**HTTP Session:**
- Used to store request parameters for future use, providing session management in web applications.
- Accessed using the `getSession()` method, creating or retrieving an HttpSession object.
- HttpSession methods include `invalidate()`, `setMaxInactiveInterval()`, `setAttribute()`, `getAttribute()`, and `removeAttribute()`.
- Advantages include no size restrictions, independence from client browsers, and security.
- Disadvantage: Creation of HttpSession objects for each user can reduce performance.

**JDBC API Drawbacks:**
- Programmers need to handle SQL-related properties and credentials manually.
- SQL queries need to be written explicitly.
- No direct conversion between Java classes and database tables.
- Lengthy code and repetitive CRUD (Create, Read, Update, Delete) operations.

**ORM (Object Relational Mapping):**
- Converts Java objects to relational databases and vice versa, simplifying database interaction.
- Overcomes JDBC drawbacks by eliminating the need for manual SQL queries.
- Popular frameworks include Hibernate, EclipseLink, and OpenJPA.
- Hibernate, for instance, is an open-source ORM tool with faster performance and JPA (Java Persistence API) implementation.

**Hibernate Mapping:**

Hibernate mapping is a crucial aspect of ORM (Object Relational Mapping) that establishes the relationship between Java classes (entities) and database tables. It allows developers to define how data is stored in the database and how it is mapped back to Java objects. Here are the key points regarding Hibernate mapping:

- **Types of Mapping:**
  - **OneToOne:** Represents a one-to-one relationship between two entities, where each record in one table is associated with exactly one record in another table. For example, the relationship between a person and their passport.
  - **OneToMany:** Represents a one-to-many relationship, where one entity is associated with multiple instances of another entity. For instance, a company having multiple employees.
  - **ManyToOne:** Represents a many-to-one relationship, where multiple instances of one entity are associated with a single instance of another entity. For example, multiple employees belonging to one department.
  - **ManyToMany:** Represents a many-to-many relationship, where multiple instances of one entity are associated with multiple instances of another entity. For instance, students enrolled in multiple courses and courses having multiple students.

- **Bi-directional Mapping:**
  - Allows accessing data in both directions, providing flexibility and convenience in querying.
  - Involves defining relationships in both entities and specifying the owning and non-owning sides of the association.
  - Helps avoid redundancy and optimize database queries by mapping entities efficiently.

- **Mapping Annotations:**
  - Annotations such as `@OneToOne`, `@OneToMany`, `@ManyToOne`, and `@ManyToMany` are used to define relationships between entities.
  - Additional attributes like `mappedBy` and `@JoinColumn` help customize the mapping behavior and optimize database schema.

**JPQL (Java Persistence Query Language):**

JPQL is a query language used in JPA (Java Persistence API) for querying entities stored in a relational database. It provides a database-agnostic way of querying data using entity names and properties, rather than SQL tables and columns. Here's a deeper look into JPQL:

- **Purpose:**
  - JPQL simplifies the querying process by using Java entities and properties instead of SQL tables and columns.
  - It ensures portability across different ORM frameworks, allowing developers to switch between frameworks without changing queries.

- **Key Features:**
  - **Entity-Centric Queries:** JPQL queries are based on Java entities and their relationships, making them more intuitive and object-oriented.
  - **Parameterized Queries:** Supports both positional and named parameters for flexible and dynamic querying.
  - **Database Agnostic:** Allows writing queries without referencing database-specific details, promoting database independence.

- **Advantages:**
  - Provides a standardized way of querying data, enhancing code readability and maintainability.
  - Supports complex querying features like joins, subqueries, and aggregate functions, facilitating advanced data retrieval operations.
  - Helps abstract database interactions, making the application more portable and scalable.

- **Example Queries:**
  - `SELECT e FROM Employee e WHERE e.department = :department`: Retrieves all employees belonging to a specific department.
  - `SELECT c FROM Course c WHERE c.students.size > 10`: Retrieves courses with more than 10 enrolled students.
  - `SELECT p FROM Product p WHERE p.price BETWEEN :minPrice AND :maxPrice`: Retrieves products within a specified price range.

JPQL plays a crucial role in building database-agnostic applications and simplifying data retrieval operations in JPA-based projects.


**Fetch Types:**
- Defines how Hibernate fetches data: EAGER (immediate loading) or LAZY (lazy loading).
- FetchType enum supports EAGER and LAZY loading types, allowing developers to control data retrieval.
- Default fetch types vary based on the mapping type, ensuring efficient data loading based on the application's needs.

**Hibernate Life Cycle (SLE):**
- Describes the various states of Hibernate-managed entities, including transient, persistent, detached, and removed states.
- Lifecycle transitions occur based on operations performed on entities, such as saving, updating, or deleting.
