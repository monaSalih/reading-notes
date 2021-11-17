# Hash Tables

Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.
![](https://www.google.com/url?sa=i&url=https%3A%2F%2Fen.wikipedia.org%2Fwiki%2FHash_table&psig=AOvVaw0FcvOKyi7bV_mJSdaQbNek&ust=1637254025294000&source=images&cd=vfe&ved=0CAsQjRxqFwoTCJjc2drsn_QCFQAAAAAdAAAAABAD)

Buckets - A bucket is what is contained in each index of the array of the hashtable. Each index is a bucket. An index could potentially contain multiple key/value pairs if a collision occurs.
![](https://www.google.com/url?sa=i&url=https%3A%2F%2Fdatabricks.com%2Fglossary%2Fhash-buckets&psig=AOvVaw2oXrA4ljTTraT6u2vTgiKJ&ust=1637254076421000&source=images&cd=vfe&ved=0CAsQjRxqFwoTCODlifHsn_QCFQAAAAAdAAAAABAD)

Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable.

![](https://miro.medium.com/max/380/0*etZsiPebZqEBXaI5.png)

----

## Why do we use them?
1. Hold unique values
2. Dictionary
3. Library
----
Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.
----

**The basic idea**
 is the ability to store the key into this data structure, and quickly retrieve the value. This is done through what we call a hash
----

## Creating a Hash
A hashtable traditionally is created from an array 
The Hash table data structure stores elements in key-value pairs where

* Key- unique integer that is used for indexing the values
* Value - data that are associated with keys.

In the following hash table, a new index is processed using the keys. And, the element corresponding to that key is stored in the index. This process is called hashing.

![](https://cdn.programiz.com/sites/tutorial2program/files/Hash-2_0.png)


Let k be a key and h(x) be a hash function.

Here, h(k) will give us a new index to store the element linked with k.
-----
## Hash Collision
, the worst possible hash is one that hashes every single key to the same exact index of an array. The more keys you have hashed to a specific index, the more key/value pair combos you can potentially have.

What would happen if two different keys resolved to be the same index of the array?
If two keys ever ultimately resolved to the same index, then two calls to .Add(key, val) with different keys would overwrite each other.
----
## solved Collisions:
by changing the initial state of the buckets. Instead of starting them all as null we can initialize a LinkedList

 if two keys resolve to the same index in the array then their key/value pairs can be stored as a node in a linked list. 
- Hash maps do this to store values:
* accept a key
* calculate the hash of the key
* use modulus to convert the hash into an array index
* store the key with the value by appending both to the end of a linked list

- Hash maps do this to read value:
* accept a key
* calculate the hash of the key
* use modulus to convert the hash into an array index
* use the array index to access the short LinkedList representing a bucket
* search through the bucket looking for a node with a key/value pair that matches the key you were given
----

## Bucket Sizes
- Hash Maps can have any number of buckets. 
- If a hash map has only a few buckets it will be densely full and have many collisions.
- If a hash map has more buckets it will be more sparsely populated, there will be less collisions.