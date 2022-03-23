# Related Resources and Integration Testing

## One-to-Many Relationship

A one-to-many relationship refers to the relationship between two entities/tables A and B in which one element/row of A may only be linked to many elements/rows of B, but a member of B is linked to only one element/row of A.

***@OneToMany*** **Annotation**

A one-to-many relationship between two entities is defined by using the @OneToMany annotation in Spring Data JPA. It declares the mappedBy element to indicate the entity that owns the bidirectional relationship. Usually, the child entity is one that owns the relationship and the parent entity contains the @OneToMany annotation.


Example:

```
@Entity
public class Book {

    @Id
    @GeneratedValue
    private long id;
    
    @Column(nullable=false)
    private String title;
    
    @ManyToOne
    @JoinColumn(name="library_id")
    private Library library;
    
    // standard constructor, getter, setter
}
```

```
public class Library {
 
    //...
 
    @OneToMany(mappedBy = "library")
    private List<Book> books;
 
    //...
 
}
```

after create Data Model we need to create a BookRepository 

```
public interface BookRepository extends CrudRepository<Book, Long> { }
```



## Integration Testing in Spring

When we talk about integration testing for a spring boot application, it is all about running an application in ApplicationContext and run tests. Spring Framework does have a dedicated test module for integration testing. It is known as spring-test. If we are using spring-boot, then we need to use spring-boot-starter-test which will internally use spring-test and other dependent libraries. 



**first of all we need to install maven dependency**

```
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-engine</artifactId>
    <version>5.8.1</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.8.1</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-test</artifactId>
    <version>5.3.3</version>
    <scope>test</scope>
</dependency>
```

For effective asserting of results, we'll also use Hamcrest and JSON path:

```
<dependency>
    <groupId>org.hamcrest</groupId>
    <artifactId>hamcrest-library</artifactId>
    <version>2.2</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>com.jayway.jsonpath</groupId>
    <artifactId>json-path</artifactId>
    <version>2.5.0</version>
    <scope>test</scope>
</dependency>
```

 Enable Spring in Tests With JUnit 5

JUnit 5 defines an extension interface through which classes can integrate with the JUnit test.

We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.

We'll also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.

```
@ExtendWith(SpringExtension.class)
@ContextConfiguration(classes = { ApplicationConfig.class })
@WebAppConfiguration
public class GreetControllerIntegrationTest {
    ....
}
```

Mocking Web Context Beans

MockMvc provides support for Spring MVC testing. It encapsulates all web application beans and makes them available for testing.

```
private MockMvc mockMvc;
@BeforeEach
public void setup() throws Exception {
    this.mockMvc = MockMvcBuilders.webAppContextSetup(this.webApplicationContext).build();
}
```

**Verify View Name test**

```
@Test
public void givenHomePageURI_whenMockMVC_thenReturnsIndexJSPViewName() {
    this.mockMvc.perform(get("/homePage")).andDo(print())
      .andExpect(view().name("index"));
}
```

- perform() method will call a GET request method, which returns the ResultActions. Using this result, we can have assertion expectations about the response, like its content, HTTP status, or header.
- andDo(print()) will print the request and response. This is helpful to get a detailed view in case of an error.
- andExpect() will expect the provided argument. In our case, we're expecting “index” to be returned via MockMvcResultMatchers.view().

**Verify Response Body**

We'll invoke the /greet endpoint from our test .

The expected output will be:
```
{
    "id": 1,
    "message": "Hello World!!!"
}
```

```
@Test
public void givenGreetURI_whenMockMVC_thenVerifyResponse() {
    MvcResult mvcResult = this.mockMvc.perform(get("/greet"))
      .andDo(print()).andExpect(status().isOk())
      .andExpect(jsonPath("$.message").value("Hello World!!!"))
      .andReturn();
    
    Assert.assertEquals("application/json;charset=UTF-8", 
      mvcResult.getResponse().getContentType());
}
```

- andExpect(MockMvcResultMatchers.status().isOk()) will verify that response HTTP status is Ok (200). This ensures that the request was successfully executed.
- andExpect(MockMvcResultMatchers.jsonPath(“$.message”).value(“Hello World!!!”)) will verify that the response content matches with the argument “Hello World!!!” Here, we used jsonPath, which extracts the response content and provides the requested value.
- andReturn() will return the MvcResult object, which is used when we have to verify something that isn't directly achievable by the library. In this case, we've added assertEquals to match the content type of the response that is extracted from the MvcResult object.


resources : 

[One-to-Many Relationship](https://www.baeldung.com/spring-data-rest-relationships#one-to-many-relationship)

[Integration Testing in Spring](https://www.baeldung.com/integration-testing-in-spring)
