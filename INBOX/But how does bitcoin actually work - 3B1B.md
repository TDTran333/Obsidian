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

What it is is a ledger; the history of transactions is the currency.

Everyone keeps their own copy of the ledger.

How can you be sure that everyone else is recording the same transactions in the same order? Can you come up with a protocol on how to accept or reject transactions and in what order so that you can feel confident that anyone else in the world following the same protocol has a personal ledger that looks the same as yours?

At a high level, the solution Bitcoin offers to trust whichever ledger has the most computational work put into it. The main tool is cryptographic has functions.

A hash function takes in any kind of message or file, and outputs a string of bits with a fixed length, like 256 bits. This output is called the "hash" or "digest" of the message, and it's meant to look random. It's infeasible to compute in the reverse direction. Hashes are 1 way. There are an infinite number of inputs that can result in the same hash output.

Interestingly, there's no proof that it's hard to compute in the reverse direction, yet a huge amount of modern security depends on cryptographic hash functions.

When you put a random number at the end of the list of transaction, and apply SHA256 to the entire thing, what should be that number so that for example, the first 30 bits of the output are zeros. The only way to find the special number is guessing and checking.

You can verify they went through a large amount of working without having to go through that same effort yourself. This is called a "proof of work". And importantly, all this work is instrinsically tied to that list of transacitions. If you change one of the transactions, even slightly, it would completely change the hash, so you have to go through the guesses to find another proof of work.

The core idea behind the original bitcoin paper is to have everybody trust whichever ledger has the most work put into it. The way this work is to first organize a given ledger into blocks, where each block consists of a list of transactions, together with a proof of work.

In the same way that a transaction is only valid if it is signed by the sender, a block is considered valid if it had a proof of work. Also, to make sure there is a standard way to order these blocks, we'll make it so that a block has to contain the hash of the previous block. That way, if you change any block, or try to swap the order of two blocks, it would change that block's hash, which changes the next block, and so on. That would require redoing all the work, finding a new special number for each of these blocks. Because blocks are chained together like this, instead of calling it a ledger, this is commonly called a "Blockchain".

Anyone in the world can be a block creator. They'll listen for transactions, collect them into a block, then do a bunch of work to find the special number that make the hash of the block fit the requirement and broadcast out the block they found.

To reward a block creator for all this work, they get some currency that doesn't come from anyone. It also means that the total money supply increases with each new block. Creating blocks is often called "mining" since it requires a lot of work, and it introduces new bits of currency into the economy.

From the miners perspective, each block is like a miniature lottery, where everyone is guessing numbers as fast as they can until one lucky individual finds one that solves the puzzle and gets rewarded for doing so.

For anyone else who wants to use the system to make payments, instead of listening for transactions, you listen for new blocks being broadcast by miners, updating your own personal copy of the blockchain. 

The key addition to the protocol is that if you hear of two distinct blockchains with conflicting transaction histories, you defer to the longest one, the one with the most work put into it. If there's a tie, wait until you hear of an additional block that makes one longer.

So even though there is no central authority, and everyone is maintaining their own copy of the blockchain, if everyone agrees to give preference to whichever blockchain has the most work put into it, we have a way to arrive at decentralized consensus.

What would it take to fool someone in this system? But unless you have 51% of the computing resource among all miners, the probability become overwhelming that the blockchain that all the other miners are working on grows faster than the fraudulent blockchain.

Notice that means you shouldn't necessarily trust a new block you hear immediatly. Instead you should wait for several new blocks to be added on top of it.

Main ideas of bitcoin
* Digital signatures
* The ledger is the currency
* Decentralize
* Proof of work
* Blockchain

The way the actual bitcoin protocol works is to periodically change that number of zeros at the start of the hash so that it should take, on average, 10 minutes to find a block. So as there are more and more miners on the network, the challenge gets harder and harder in such a way that this miniature lottery only has about one winner every 10 minutes.

Many newer cryptocurrencies have much shorter block times. ETH 15 sec, XRP 3.5 sec, LTC 2.5 min.

All the money in Bitcoin ultimately comes from some block reward. 50 btc per block initially.
https://blockexplorer.one/btc/mainnet/

Every 210,000 blocks, which is about every 4 years, the reward gets cut in half. Because the reward decreases geometrically over time, there will never be more than 21 million bitcoin in existence.

This doesn't mean that miners will stop making money. In addition to the block reward, miners can also pick up transaction fees. The way this works is that whenever you make a payment, you can optionally include a small transaction fee with it that will go to the miner of whatever block includes that payment.  The reason you might do this is to incentivize miners to actually include the transaction that you broadcast into the next block.

In Bitcoin, each block is limited to about 2,400 transactions, which many critics argue is unnecessarily restrictive. For comparison, Visa processes an average of 1,700 transaction per second, and they're capable of handling more than 24,000 per second. Slower processing on Bitcoin means higher transaction fees, since that's what determine which transactions miners choose to include in a new block.

Other topics:
Merkle trees
Alternatives to proof of work
Scripting

2^256 = 4bilx4bilx4bilx4bilx4bilx4bilx4bilx4bil 
==> 1/4bil chance if ran for 37xAge of the universe
2^32 = 4 billion

In jul 2017: 5 billion billion hashes/second from all miners

A good GPU = 1bil/sec

Application Specific Integrated Circuit are a thousand time better than GPU
trillion hashes/sec