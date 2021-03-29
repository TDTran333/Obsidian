---
aliases:
tags: crypto, finance
---
Link: [YouTube](https://www.youtube.com/watch?v=bBC-nXj3Ng4)

# But how does bitcoin actually work?

What does it mean to have a Bitcoin?
Fully digital currency
No government to issue it
No bamks to manage account and verify transactions

Who is Satoshi Nakamoto?

Digital signatures
Proof of work
Cryptographic hash functions

Ledger - Trust + Cryptography = Cryptocurrency

You don't need to know the details to use cryptocurrency just like you don't need to know the details of what happens under the hood when you swipe a credit card.

The difference is that the backbone underlying this is not a bank verifying transactions but a system of decentralized trustless verification based on some born in cryptography.

Ledger and digital signatures

What stop someone from forging/adding a line to the public ledger?

Digital signatures
Public key / Private (secret) key pair
pk / sk

Producing a signature is a function that depend on the message itself and your private key.
The private key ensures that only you can produce the signature, and the fact that it depends on the message means no one can just copy one of your signatures to forge it on another message.

Hand-in-hand is a function to verify that a signature is valid and this is where the public key come in play. All it does is output true or false if this was a signature created by the private key associated with the public key you use for the verification.

The idea it is that it should be completely infeasible to find a valid signature if you don't know the secret key. Specifically there is no strategy better than just guessing and checking if random signatures are valid using the public key until you hit one that works.

There are 2^(256) possible signatures with 256 bits.

When you sign a transaction, the message has to also include some unique id associated with that transaction. Each line would have a new signature.

Instead of requiring to pay the debt at the end of the period, what if everyone put in an amount in the system and set the rule to make overspending invalid. 
This would require to know the full history of the transactions.

This step remove the connection between the ledger and physical cash.