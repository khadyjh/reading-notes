# Spring Authorization
Authorization is determining who is allowed to access a particular resource.

in other word authorized mean what level you can access , let's imagine a website has simple user and admin 

the user can access the home page but the admin has the ability to access the database .
here when Authorization come out

to make user authorized  you need to create a class called **WebSecurityConfig.java**
in this class you need to override method 
```
protected void configure(final HttpSecurity http) throws Exception {

  http.cors().disable().csrf().disable()
               .authorizeRequests()
               .antMatchers("/admin*").hasRole("ADMIN") 
               .antMatchers("/user*").hasRole("USER") 
               .antMatchers("/").permitAll() 
} 
```

thats mean only admin role can access admin endpoint and only user can access user endpoint 
but the root endpoint access by all even if not user or admin 


## Securing the Application with GitHub and Spring Security

if the website use GitHub authorization then in OAuth 2.0 terms, is a Client Application, and it uses the authorization code grant to obtain an access token from GitHub (the Authorization Server).

It then uses the access token to ask GitHub for some personal details (only what you permitted it to do), including your login ID and your name. In this phase, GitHub is acting as a Resource Server, decoding the token that you send and checking if it gives the app permission to access the user’s details. If that process is successful, the app inserts the user details into the Spring Security context so that you are authenticated.






resources 

[Link](https://spring.io/guides/tutorials/spring-boot-oauth2/)

[Link](https://www.youtube.com/watch?v=payxWrmF_0k)