---
aliases:
tags: blockchain
---
Link: [Investopedia](https://www.investopedia.com/terms/m/merkle-tree.asp), [website](https://brilliant.org/wiki/merkle-tree/)

# What is a Merkle Tree?
A Merkle tree is a data structure that is used in computer science applications. In bitcoin and other cryptocurrencies, Merkle trees serve to encode blockchain data more efficiently and securely.

They are also referred to as "binary hash trees."

Each transaction is hashed, then each pair of transactions is concatenated and hashed together, and so on until there is one hash for the entire block. (If there is an odd number of transactions, one transaction is doubled and its hash is concatenated with itself.)

The hashes on the bottom row are referred to as "leaves," the intermediate hashes as "branches," and the hash at the top as the "root." The Merkle root of a given block is stored in the header.

The Merkle tree is useful because it allows users to verify a specific transaction without downloading the whole blockchain.

Merkle trees are named after Ralph Merkle, who proposed them in a 1987 paper titled "[A Digital Signature Based on a Conventional Encryption Function.](http://people.eecs.berkeley.edu/~raluca/cs261-f15/readings/merkle.pdf)" Merkle also invented cryptographic hashing.

The reason that Merkle trees are useful in distributed systems is that it is inefficient to check the entirety of file to check for issues. The reason that Merkle trees are useful in peer-to-peer systems is that they help you verify information, even if some of it come from an untrusted source (which is a concern in peer-to-peer systems).

