# Spring Authentication
## Spring security architecture

Spring security is framework used for securing Spring applications. It stands between client and application and gives possibility of configuring what data and functionalities are exposed to which users.

**two concepts in spring security :**
- authentication (who are you?) 
-  authorization (what are you allowed to do?)

### Authentication

to  authenticate your application in spring you have to use AuthenticationManager interface which have only one method 

```
public interface AuthenticationManager {
  Authentication authenticate(Authentication authentication) throws AuthenticationException;
}
```

The **authenticate()** method can return an Authentication if the input represents a **valid principal** in that case it Normally **returns authenticated=true** . It will **throw an AuthenticationException** if the input represents an **invalid principal**. It will **return null** if it **can’t decide whether the input value is valid or invalid**.



AuthenticationException is a runtime exception its usually depending  on the style or purpose of the application , a web UI might render a page that says that the authentication failed, and a backend HTTP service might send a 401 response

### Authorization or Access Control

Authorization process starts when authentication process completes. AccessDecisionManager interface is the core entity in the authorization process. Spring security framework provides three implementations of AccessDecisionManager interface and all three delegate to a chain of AccessDecisionVoter.

```
boolean supports(ConfigAttribute attribute);

boolean supports(Class<?> clazz);

int vote(Authentication authentication, S object,
        Collection<ConfigAttribute> attributes);
```


resources

[Spring Authentication](https://spring.io/guides/topicals/spring-security-architecture/)

