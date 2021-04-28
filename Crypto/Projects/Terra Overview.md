---
aliases: LUNA
tags: crypto
---
Link: [Summary](https://www.yeetfi.com/luna/), [[Terra Money - Stability and Adoption|Terra White Paper]]

# Terra overview
### **What’s the story?**
-   Payments made simple
-   Price stable currencies

### **Competition**
-   MTA
-   MakerDAO

### **LUNA coin is used for**
-   Staking to validate blocks
-   Staking to provide price feeds
-   Keep Terra currencies at their peg
-   Governance

### **What is Terra?**
Terra is a proof of stake blockchain created for **price-stable** cryptocurrencies with a focus on **payments** and **commerce**.

### **How it works**
**Terra uses PoS Tendermint BFT consensus**
-   dPoS-like scheme driven by a set of 100 top validators.
-   Blocks every 6 seconds.
-   Miners need to stake LUNA to mine Terra transactions.
-   At every block period, the protocol elects a block producer from the set of staked miners, weighted by the size of the active miner’s Luna stake.

### **Terra stable currencies**
-   **Pegged to USD, EUR, CNY, JPY, GBP, KRW, and the IMF SDR.**
-   Users can convert TerraKRW for TerraUSD instantly at the effective KRW/USD exchange rate.

### **Oracle price feeds**
-   For any Terra sub-currency – TerraKRW, TerraUSD, TerraSDR – miners submit a vote for what they believe to be the current exchange rate in the target fiat asset.
-   Taking the weighted medians as the true rates.
-   Those who voted 1 standard deviation of the elected median are rewarded. Those who voted outside may be punished via slashing of their stakes.

### **Price stability**
  The system uses Luna to stabilize the price of Terra currencies by agreeing to be counter-party to anyone looking to swap Terra and Luna at Terra’s target exchange rate.
-   Price < 1 SDR, users and arbitragers can send 1 TerraSDR to the system and receive 1 SDR’s worth of Luna.
-   Price > 1 SDR, users and arbitragers can send 1 SDR’s worth of Luna to the system and receive 1 TerraSDR.

### **LUNA supply**
-   Volatility is moved from Terra price to Luna supply.
-   This Luna dilution presents a problem for miners; their Luna stakes are worth a smaller portion of total available mining power post-contraction.
-   The system burns a portion of the Luna supply until it has reached its 1 billion equilibrium.

### **Miner rewards**
-   Transactions fees default to 0.1% and are capped at 1%.
-   When demand for Terra increases, the system mints Terra and earns Luna in return. This is called seignorage.
-   Miners voting within the median for price feeds of price earn rewards from the seignorage.
-   The system burns a portion of earned Luna, making mining power scarcer.

