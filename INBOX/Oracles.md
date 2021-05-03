---
aliases:
tags: crypto
---
Link: [Website](https://www.reddit.com/r/CryptoCurrency/comments/mgak48/defi_explained_oracles/)

# Oracles
### What is a blockchain Oracle?
Blockchains cannot retrieve or send data themselves to an external problem. This function is not built into the blockchain itself.

As a result, blockchains are actually isolated networks that look suspiciously like a computer without an Internet connection. And that isolation is precisely what makes the blockchain so secure, because no one can access it just like that.

However, smart contracts must be connected to the outside world, so that they can be used in as many situations as possible. For example, smart contracts in the financial world need market information to pay for settlements, and smart contracts in the insurance world need certain information to make decisions about policy payments.

Blockchain Oracles therefore provide the data necessary to be able to execute smart contracts when the set conditions are met. A blockchain Oracle is the only way for the blockchain to communicate with the outside world.

For technical accuracy,  it is not the case that oracle smart contracts have access to the outside world. Rather, oracle smart contracts contain one or more variables (representing some information about the outside world) which must be continuously updated by the Oracle operators.

When your smart contract queries an Oracle for some information, this information does not come from the outside world directly. Rather the information returned is simply the information stored in the oracle smart contract which is, presumably, up to date with the outside world.

### What does a blockchain Oracle do?
 Oracles' key features:
-   Listens to the blockchain network to check for requests to fetch data outside the network to make smart contracts work.
-   Retrieve data from different types of systems in order to be able to offer the requested data.
-   Convert data to the correct format in order to allow different systems to communicate with each other. A blockchain cannot just communicate with any other system, because they are different programming languages, have different system requirements, etc. The Oracle takes care of the compatibility.
-   Validate performance with a cryptographic proof that certain transactions, signatures and executions actually took place.
-   Make calculations on data. Consider, for example, calculating the median, as well as performing more complex tasks, such as generating insurance quotations based on different types of data.
-   Sending data and evidence to the blockchain and other systems, so that they can then perform the necessary actions. For example, smart contracts can perform actions based on the data that the Oracle sends.

In order to provide the above functions, the Oracle must work on and off the blockchain at the same time. The part that sits on the blockchain is there for establishing a blockchain connection (to listen for requests), broadcast data, send evidence, convert blockchain data and sometimes perform calculations on the blockchain.

The portion that works outside of the blockchain is for processing requests, retrieving and formatting external data, sending blockchain data to external systems, and possibly performing calculations in more advanced Oracle networks.

### Betting is an example of application of an Oracle

### Chainlink and Band Protocol as Oracle platforms
The main difference between Chainlink and Band Protocol is that Band Protocol uses its own blockchain called BandChain, based on Tendermint, with a Delegated Proof of Stake (DPoS) consensus algorithm. It works in the Cosmos ecosystem. Chainlink, on the other hand, is not a blockchain, it is a kind of network of nodes that only work when oracles are solely focused on delivering data between entities. There is no blockchain of its own, because it is all based on Ethereum.
