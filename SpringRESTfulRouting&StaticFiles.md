# Spring RESTful Routing & Static Files

Spring Data repository interfaceses 
  - CrudRepository
  - PagingAndSortingRepository
  - JpaRepository

  Each one defines its own functionality:

 - CrudRepository provides CRUD functions
 - PagingAndSortingRepository provides methods to do pagination and sort records
 - JpaRepository provides JPA related methods such as flushing the persistence context and delete records in a batch

 ## CrudRepository

 ```
public interface CrudRepository<T, ID extends Serializable>
  extends Repository<T, ID> {

    <S extends T> S save(S entity);

    T findOne(ID primaryKey);

    Iterable<T> findAll();

    Long count();

    void delete(T entity);

    boolean exists(ID primaryKey);
}
 ```

 Notice the typical CRUD functionality:

- save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
- findOne(…) – get a single entity based on passed primary key value
- findAll() – get an Iterable of all available entities in database
- count() – return the count of total entities in a table
- delete(…) – delete an entity based on the passed object
- exists(…) – verify if an entity exists based on the passed primary key value

This interface looks quite generic and simple, but actually, it provides all basic query abstractions needed in an application.

## JpaRepository

```
public interface JpaRepository<T, ID extends Serializable> extends
  PagingAndSortingRepository<T, ID> {

    List<T> findAll();

    List<T> findAll(Sort sort);

    List<T> save(Iterable<? extends T> entities);

    void flush();

    T saveAndFlush(T entity);

    void deleteInBatch(Iterable<T> entities);
}
```
- findAll() – get a List of all available entities in database
- findAll(…) – get a List of all available entities and sort them using the provided condition
- save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
- flush() – flush all pending task to the database
- saveAndFlush(…) – save the entity and flush changes immediately
- deleteInBatch(…) – delete an Iterable of entities. Here, we can pass multiple objects to delete them in a batch

# Accessing Data with JPA

**Define a Simple Entity**

```
package com.example.accessingdatajpa;

import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.GenerationType;
import javax.persistence.Id;

@Entity
public class Customer {

  @Id
  @GeneratedValue(strategy=GenerationType.AUTO)
  private Long id;
  private String firstName;
  private String lastName;

  protected Customer() {}

  public Customer(String firstName, String lastName) {
    this.firstName = firstName;
    this.lastName = lastName;
  }

  @Override
  public String toString() {
    return String.format(
        "Customer[id=%d, firstName='%s', lastName='%s']",
        id, firstName, lastName);
  }

  public Long getId() {
    return id;
  }

  public String getFirstName() {
    return firstName;
  }

  public String getLastName() {
    return lastName;
  }
}
```

Here you have a Customer class with three attributes: id, firstName, and lastName. You also have two constructors. The default constructor exists only for the sake of JPA. You do not use it directly, so it is designated as protected. The other constructor is the one you use to create instances of Customer to be saved to the database.

The Customer class is annotated with @Entity, indicating that it is a JPA entity. (Because no @Table annotation exists, it is assumed that this entity is mapped to a table named Customer.)

The Customer object’s id property is annotated with @Id so that JPA recognizes it as the object’s ID. The id property is also annotated with @GeneratedValue to indicate that the ID should be generated automatically.

The other two properties, firstName and lastName, are left unannotated. It is assumed that they are mapped to columns that share the same names as the properties themselves.

The convenient toString() method print outs the customer’s properties.


**Create Simple Queries**

Spring Data JPA focuses on using JPA to store data in a relational database. Its most compelling feature is the ability to create repository implementations automatically, at runtime, from a repository interface.

```
package com.example.accessingdatajpa;

import java.util.List;

import org.springframework.data.repository.CrudRepository;

public interface CustomerRepository extends CrudRepository<Customer, Long> {

  List<Customer> findByLastName(String lastName);

  Customer findById(long id);
}
```

CustomerRepository extends the CrudRepository interface. The type of entity and ID that it works with, Customer and Long, are specified in the generic parameters on CrudRepository. By extending CrudRepository, CustomerRepository inherits several methods for working with Customer persistence, including methods for saving, deleting, and finding Customer entities.

Spring Data JPA also lets you define other query methods by declaring their method signature. For example, CustomerRepository includes the findByLastName() method.

In a typical Java application, you might expect to write a class that implements CustomerRepository. However, that is what makes Spring Data JPA so powerful: You need not write an implementation of the repository interface. Spring Data JPA creates an implementation when you run the application.

**Create an Application Class**

@SpringBootApplication is a convenience annotation that adds all of the following:

@Configuration: Tags the class as a source of bean definitions for the application context.

@EnableAutoConfiguration: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings. For example, if spring-webmvc is on the classpath, this annotation flags the application as a web application and activates key behaviors, such as setting up a DispatcherServlet.

@ComponentScan: Tells Spring to look for other components, configurations, and services in the com/example package, letting it find the controllers.

```
package com.example.accessingdatajpa;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import org.springframework.boot.CommandLineRunner;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.context.annotation.Bean;

@SpringBootApplication
public class AccessingDataJpaApplication {

  private static final Logger log = LoggerFactory.getLogger(AccessingDataJpaApplication.class);

  public static void main(String[] args) {
    SpringApplication.run(AccessingDataJpaApplication.class);
  }

  @Bean
  public CommandLineRunner demo(CustomerRepository repository) {
    return (args) -> {
      // save a few customers
      repository.save(new Customer("Jack", "Bauer"));
      repository.save(new Customer("Chloe", "O'Brian"));
      repository.save(new Customer("Kim", "Bauer"));
      repository.save(new Customer("David", "Palmer"));
      repository.save(new Customer("Michelle", "Dessler"));

      // fetch all customers
      log.info("Customers found with findAll():");
      log.info("-------------------------------");
      for (Customer customer : repository.findAll()) {
        log.info(customer.toString());
      }
      log.info("");

      // fetch an individual customer by ID
      Customer customer = repository.findById(1L);
      log.info("Customer found with findById(1L):");
      log.info("--------------------------------");
      log.info(customer.toString());
      log.info("");

      // fetch customers by last name
      log.info("Customer found with findByLastName('Bauer'):");
      log.info("--------------------------------------------");
      repository.findByLastName("Bauer").forEach(bauer -> {
        log.info(bauer.toString());
      });
      // for (Customer bauer : repository.findByLastName("Bauer")) {
      //  log.info(bauer.toString());
      // }
      log.info("");
    };
  }

}
```


resources

[CrudRepository, JpaRepository,](https://www.baeldung.com/spring-data-repositories)

[Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)