-->We will build a Spring Boot JPA Rest CRUD API for a Tutorial application in that:

Each Tutotial has id, title, description, published status.
Apis help to create, retrieve, update, delete Tutorials.
Apis also support custom finder methods such as find by published status or by title.

-->TECHNOLOGY:
Java 8
Spring Boot 2.2.1 (with Spring Web MVC, Spring Data JPA)
PostgreSQL/MySQL
Maven 3.6.1

-->Use Spring web tool or your development tool (Spring Tool Suite, Eclipse, Intellij) to create a Spring Boot project.

-->Then open pom.xml and add dependencies

-->We also need to add one more dependency.
– If you want to use MySQL:
<dependency>
	<groupId>mysql</groupId>
	<artifactId>mysql-connector-java</artifactId>
	<scope>runtime</scope>
</dependency>


-->Under src/main/resources folder, open application.properties and write these lines.
 For MySQL:

spring.datasource.url= jdbc:mysql://localhost:3306/testdb?useSSL=false
spring.datasource.username= root
spring.datasource.password= 123456

spring.jpa.properties.hibernate.dialect= org.hibernate.dialect.MySQL5InnoDBDialect

Hibernate ddl auto (create, create-drop, validate, update)
spring.jpa.hibernate.ddl-auto= update


-->Our Data model is Tutorial with four fields: id, title, description, published.
In model package, we define Tutorial class.

model/Tutorial.java


-->Create Repository Interface
Let’s create a repository to interact with Tutorials from the database.
In repository package, create TutorialRepository interface that extends JpaRepository.

repository/TutorialRepository.java


->>Create Spring Rest APIs Controller
Finally, we create a controller that provides APIs for creating, retrieving, updating, deleting and finding Tutorials.

controller/TutorialController.java

-->Run Spring Boot application with command: mvn spring-boot:run.

-->tutorials table will be automatically generated in Database.
