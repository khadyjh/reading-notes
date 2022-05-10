# Hash Tables
data structure used to save data as key and value pairs 

usually we use array to store the data but then it hard to search because the time complexity for array searching is O(n)

so as an optimization we can use a key value to link it with the actual value, so it can be accessed in O(1) time complexity
and that is what the hash table does 

The idea of hashing is to distribute entries (key/value pairs) uniformly across an array. 
Each element is assigned a key (converted key). By using that key you can access the element in O(1) time. Using the key, the algorithm (hash function) computes an index that suggests where an entry can be found or inserted.

### hashing 
a hash code turns a key into an integer. It’s very important that hash codes are always the same:
their output is determined only by their input. Hash codes should never have randomness to them.
The same key should always produce the same hash code.

### methods 

- add()
- find()
- contains()
- getHash()


resources

[Basics of Hash Tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)

[Hashtables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)

[what is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0)

[hash table wiki](https://en.wikipedia.org/wiki/Hash_table)