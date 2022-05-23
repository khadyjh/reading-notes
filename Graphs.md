# Graphs  
a graph is non-Linear data structure consist of nods and edges 

## Directed vs Undirected
### Undirected
graph where link between two node is bidirectional 
 


### Directed 
graph where link between two node is one direction




## Complete vs Connected vs Disconnected
### Complete
when each node have linked to all others node  
### Connected
when all node have at least one link to other nodes 
### Disconnected
when some node may not have linked to other node 

## Acyclic vs Cyclic
### Acyclic
when graph is directed and didn't have cycles (no loop)
### Cyclic
when graph is directed and have cycles 


## Graph Representation
### Adjacency Matrix
when the graph represent as two-dimensional array (n*n) 
- if two node have edge between them then it represents as 1 in the matrix 
- if two node have no edge between them then it represents as 0 in the matrix 

a **sparse** graph is when there are very few connections. a **dense** graph is when there are many connections

### Adjacency List
when the graph represent as array of linked list  

### Weighted Graphs
when the edge in graph have a weight 

## Traversals
### Breadth First
approach where we use queue to visit all nodes level by level 
### Depth First
approach where we use stack to visit children node (in depth) then parent node 

resources

[graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)