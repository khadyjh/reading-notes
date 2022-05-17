# GraphQL @connection


## Has Many relationship
in GraphQL, we can generate one-directional / one-to-many relationship between two models using the **@hasMany** 
annotation  , which allow generating queries and mutations that allow to retrieve related data .

we can customize the attribute that used in joined table by **@index** annotation and specify the name 

~~~
type Post @model {
  id: ID!
  title: String!
  comments: [Comment] @hasMany(indexName: "byPost", fields: ["id"])
}

type Comment @model {
  id: ID!
  postID: ID! @index(name: "byPost", sortKeyFields: ["content"])
  content: String!
~~~


##  Using CompletableFuture as a Simple Future

CompletableFuture is used for asynchronous programming in Java. Asynchronous programming is a means of writing non-blocking code by running a task on a separate thread than the main application thread and notifying the main thread about its progress, completion or failure.

This way, your main thread does not block/wait for the completion of the task and it can execute other tasks in parallel.


resources

[CompletableFuture in Java (](https://www.baeldung.com/java-completablefuture#CompletableFuture)
[Has Many relationship](https://docs.amplify.aws/cli/graphql/data-modeling/#has-many-relationship)