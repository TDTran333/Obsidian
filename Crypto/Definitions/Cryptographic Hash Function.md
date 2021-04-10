---
aliases:
tags: crypto
---
Link: [Wikipedia](https://en.wikipedia.org/wiki/Cryptographic_hash_function)

# Cryptographic Hash Function
A cryptographic hash function is a mathematical algorithm that maps data of arbitrary size to a bit array of a fixed size. It is a one-way function, that is, a function which is practically infeasible to invert.

The ideal cryptographic hash function has the following main properties:

* it is deterministic, meaning that the same message always results in the same hash
* it is quick to compute the hash value for any given message
* it is infeasible to generate a message that yields a given hash value (i.e. to reverse the process that generated the given hash value)
* it is infeasible to find two different messages with the same hash value a small change to a message should change the hash value so extensively that a new hash value appears uncorrelated with the old hash value (avalanche effect)

Cryptographic hash functions have many information-security applications, notably in digital signatures, message authentication codes (MACs), and other forms of authentication. 

https://crypto.stackexchange.com/questions/45377/why-cant-we-reverse-hashes

-   **Bit dependency**: A hash algorithm is designed to ensure that each bit of the output is dependent upon every bit in the input. This prevents anyone from splitting the algorithm up and trying to reverse calculate an input from each bit of the output hash separately. In order to solve just one output bit, you have to know the entire input. In other words, when reversing a hash, it's all or nothing.
    
-   **Avalanching**: Related to bit dependency, a change in a _single bit_ in the input (from 0 to 1 or vice-versa) is designed to result in a huge change in the internal state of the algorithm and of the final hash value. Since the output changes so dramatically with each input bit change, this stops people from building up relationships between inputs and outputs (or parts thereof).
    
-   **Non-linearity**: Hashing algorithms always contain non-linear operations - this prevents people from using linear algebra techniques to "solve" the input from a given output. Note the addition example I use above is a linear operation; building a hash algorithm using just addition operators is a really bad idea! In reality, hashing algorithms use many combinations of linear and non-linear operations.
    
All of this adds up to a situation where the easiest way of finding a matching hash is just to guess a different input, hash it and see if it matches.