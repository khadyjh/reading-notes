# Room

Room is Google's new persistence library designed to make it easier to build offline apps. It tries to expose APIs that can leverage the full power of SQL while still providing an abstraction layer for managing the data as Java objects. 

Room provides the following benefits:

- Compile-time verification of SQL queries.
- Convenience annotations that minimize repetitive and error-prone boilerplate code.
- Streamlined database migration paths.

to use the Room database in your project you need to declare three component 

- database class holds the database and the server act as the main point to establish the connection for the database 

- Data entities the table you want to add to the database each class represents one table 

- Data access objects (DAOs) to hold the database query (operations)
 You can define each DAO as either an interface or an abstract class , you need to use **@Dao** annotation to declare the Data access objects component .

 
Room provides some method to allow the developers to insert, update, and delete without the use of quiery  
also the developers can provide his custom query 