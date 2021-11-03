# Read: Hash Tables

## Intro to Hash Tables

***HashTables***

* Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose.
  * In the case of a HashTable, it is used to determine the index of the array.
* Buckets - A bucket is what is contained in each index of the array of the HashTable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.
* Collisions - A collision is what happens when more than one key gets hashed to the same location of the HashTable.
* Use HashTable to hold unique values, dictionary, and library.
* HashTable - are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value. Ability to store the key into this data structure, and quickly retrieve the value through a hash.
* A hash is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.
* Ideally its Big O(1), and worst case O(n).

* A hash code turns a key into an integer, and their output is determined only by their input.
* HashTable traditionally is created from an array. Each index of the array can hold many types of values. Each Index of the array contain “buckets”, and each of these “buckets” holds one key/value pair combination.
* Collision - occurs when more than one key hashes to the same index in an array.
* Hash Maps can have any number of buckets. If a hash map has only a few buckets it will be densely full and have many collisions. If a hash map has more buckets it will be more sparsely populated, there will be less collisions, but there may be a lot of extra empty space.
* Load factor - tells us something about how full the hash table is.
* Add() - when adding a new key/value pair to a hashTable
* Find() - takes in a key, gets the Hash, and goes to the index location specified.
* Contains() - will accept a key, and return a bool on if that key exists inside the hashTable.
* GetHash() - will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.

## what is a hash table?

***Introduction to hash tables***

* Hash tables are used to store information.
* Has two main components: a key and a value.
* A way to implement an associative array.
* Hash function will take in a key value, and as a result will give an index number.
* The key will always match that index number, but if another key with the same index comes up, you have to make a chain off of the unit it is in.
* Hash tables can be very large, and store many key values.

## basics of hash tables

***Basics of Hash Tables***

* Hashing - is a technique that is used to uniquely identify a specific object from a group of similar objects.
* Large keys are converted into small keys by using hash functions.
* Hash function - is any function that can be used to map a data set of an arbitrary size to a data set of a fixed size, which falls into the hash table. The values returned by a hash function are called hash values, hash codes, hash sums, or simply hashes.
* The values are then stored in a data structure called hash table. Hash table is a data structure that is used to store keys/value pairs.

* Hashing basic requirements:
  * Easy to compute - It should be easy to compute and must not become an algorithm in itself.
  * Uniform distribution - It should provide a uniform distribution across the hash table and should not result in clustering.
  * Less collisions - Collisions occur when pairs of elements are mapped to the same hash value. These should be avoided.
  
* Separate chaining - is one of the most commonly used collision resolution techniques, and implemented using linked lists.
* Open addressing - all entry records are stored in the array itself. When a new entry has to be inserted, the hash index of the hashed value is computed and then the array is examined.
* Probe sequence - is the sequence that is followed while traversing through entries.
* Linear probing - is when the interval between successive probes is fixed (usually to 1).
* Quadratic probing - is similar to linear probing and the only difference is the interval between successive probes or entry slots.
* Associative arrays - arrays whose indices are arbitrary strings or other complicated objects.
* Database indexing - hash tables may also be used as disk-based data structures and database indices.
* Caches - hash tables can be used to implement caches.
* Object representation - several dynamic languages, such as Perl, Python, JavaScript, and Ruby use hash tables to implement objects.
* Hash Functions are used in various algorithms to make their computing faster.

## hash table wiki

***Hash table***

* Hash table (hash map) is a data structure that implements an associative array abstract data type, a structure that can map keys to values. A hash table uses a hash function to compute an index, also called a hash code, into an array of buckets or slots, from which the desired value can be found.

  * The idea of hashing is to distribute the entries (key/value pairs) across an array of buckets. Given a key, the algorithm computes an index that suggests where the entry can be found:

```
   index = f(key, array_size).
```

* Done in two steps:

```
   hash = hashfunc(key)
  index = hash % array_size
```

* The function should provide a uniform distribution of hash values.

* Cryptographic hash functions are believed to provide good hash functions for any table size, either by modulo reduction or by bit masking.

* Perfect hash function can be used to create a perfect hash table that has no collisions.

* A critical statistic for a hash table is the load factor, defined as load factor = n/k.

* n is the number of entries occupied in the hash table, and k is the number of buckets.

* Hash collisions are practically unavoidable when hashing a random subset of a large set of possible keys. Solutions for collisions are separate chaining and open addressing.
* Rehashing - includes increasing the size of the underlying data structure and mapping existing items to new bucket locations.
* Speed analysis - the hash function is completely unspecified and the table does not resize in the simplest model.
* Memory utilization - the memory requirement for a table needs to be minimized.
* A transposition table to a complex Hash Table which stores information about each section that has been searched.