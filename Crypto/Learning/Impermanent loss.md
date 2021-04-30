---
aliases:
tags: crypto
---
Link: [Website](https://academy.binance.com/en/articles/impermanent-loss-explained)

# Impermanent loss
Impermanent loss happens when the price of your tokens changes compared to when you deposited them in the pool.

DeFi protocols like [Uniswap](https://academy.binance.com/en/articles/what-is-uniswap-and-how-does-it-work), [SushiSwap](https://academy.binance.com/en/articles/your-guide-to-sushiswap), or [PancakeSwap](https://academy.binance.com/en/articles/a-guide-to-pancakeswap) have seen an explosion of volume and liquidity. These liquidity protocols enable essentially anyone with funds to become a market maker and earn trading fees.

### What is impermanent loss?
Impermanent loss happens when you provide liquidity to a liquidity pool, and the price of your deposited assets drop compared to when you deposited them. The loss means less dollar value at the time of withdrawal than at the time of deposit.

So why do liquidity providers still provide liquidity if they’re exposed to potential losses? Well, impermanent loss can still be counteracted by trading fees. If there’s a lot of trading volume happening in a given pool, it can be profitable to provide liquidity even if the pool is heavily exposed to impermanent loss. This, however, depends on the protocol, the specific pool, the deposited assets, and even wider market conditions.

### How does impermanent loss happen?
In their raw form, AMMs are disconnected from external markets. If token prices change on external markets, an AMM doesn’t automatically adjust its prices. It requires an arbitrageur to come along and buy the underpriced asset or sell the overpriced asset until prices offered by the AMM match external markets. During this process, the profit extracted by arbitrageurs is effectively removed from the pockets of liquidity providers, resulting in impermanent loss.

### Impermanent loss estimation
Impermanent loss happens **no matter which direction the price changes**.

-   1.25x price change = 0.6% loss
-   1.50x price change = 2.0% loss
-   1.75x price change = 3.8% loss
-   2x price change = 5.7% loss
-   3x price change = 13.4% loss
-   4x price change = 20.0% loss
-   5x price change = 25.5% loss

### The risks of providing liquidity to an AMM
As a simple rule, the more volatile the assets are in the pool, the more likely it is that you can be exposed to impermanent loss. It can also be better to start by depositing a small amount. That way, you can get a rough estimation of what returns you can expect before committing a more significant amount.

If a liquidity pool promises unusually high returns, there is probably a tradeoff somewhere, and the associated risks are likely also higher.


