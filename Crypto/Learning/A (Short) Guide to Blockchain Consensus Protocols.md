---
aliases:
tags: crypto
---
Link: [Website](https://www.coindesk.com/short-guide-blockchain-consensus-protocols)

# A (Short) Guide to Blockchain Consensus Protocols
### Proof of work
In proof of work, miners compete to add the next block (a set of transactions) in the chain by racing to solve a extremely difficult cryptographic puzzle. The first to solve the puzzle, wins the lottery. As a reward for his or her efforts, the miner receives 12.5 newly minted bitcoins – and a small transaction fee.

Common criticisms include that it requires enormous amounts of computational energy, that it does not scale well (transaction confirmation takes about 10-60 minutes) and that the majority of mining is centralized in areas of the world where electricity is cheap.

### Proof of stake
In this type of consensus algorithm, a ‘validator’ invests in the coins of the system. All the coins exist from day one, and validators (also called stakeholders, because they hold a stake in the system) are paid strictly in transaction fees. In proof of stake, your chance of being picked to create the next block depends on the fraction of coins in the system you own (or set aside for staking). Once a validator creates a block, that block still needs to be committed to the blockchain. Different proof-of-stake systems vary in how they handle this.

What is to discourage a validator from creating two blocks and claiming two sets of transaction fees? And what is to discourage a signer from signing both of those blocks? This has been called the ‘nothing-at-stake‘ problem. A participant with nothing to lose has no reason not to behave badly.

### Proof of activity
Proof of activity is a hybrid approach that combines both proof of work and proof of stake.

In proof of activity, mining kicks off in a traditional proof-of-work fashion, with miners racing to solve a cryptographic puzzle. Depending on the implementation, blocks mined do not contain any transactions (they are more like templates), so the winning block will only contain a header and the miner’s reward address.

At this point, the system switches to proof of stake. Based on information in the header, a random group of validators is chosen to sign the new block. The more coins in the system a validator owns, the more likely he or she is to be chosen. The template becomes a full-fledged block as soon as all of the validators sign it.

Fees are split between the miner and the validators who signed off on the block.

Criticisms of proof of activity are the same as for both proof of work (too much energy is required to mine blocks) and proof of stake (there is nothing to deter a validator from double signing).

### Proof of burn
With proof of burn, you ‘burn’ coins by sending them to an address where they are irretrievable. By committing your coins to never-never land, you earn a lifetime privilege to mine on the system based on a random selection process.

Over time, your stake in the system decays, so eventually you will want to burn more coins to increase your odds of being selected in the lottery.

While proof of burn is an interesting alternative to proof of work, the protocol still wastes resources needlessly. Another criticism is that mining power simply goes to those who are willing to burn more money.

### Proof of capacity
The more hard drive space you have, the better your chance of mining the next block and earning the block reward. Prior to mining in a proof-of-capacity system, the algorithm generates large data sets known as ‘plots’, which you store on your hard drive. The more plots you have, the better your chance of finding the next block in the chain.

By investing in terabytes of hard drive space, you buy yourself a better chance to create duplicate blocks and fork the system. But with proof of capacity, we still have the problem of nothing at stake to deter bad actors.

### Proof of elapsed time
Chipmaker Intel has come up with its own alternative consensus protocol called proof of elapsed time. This system works similarly to proof of work, but consumes far less electricity.

Instead of having participants solve a cryptographic puzzle, the algorithm uses a trusted execution environment (TEE) – such as SGX – to ensure blocks get produced in a random lottery fashion, but without the required work.

The one problem with this protocol is it requires you to put your trust in Intel.