https://old.reddit.com/r/wallstreetbets/comments/kcs4xy/what_quant_funds_actually_do_tldr_no_it_isnt/

### Summary 
Quants don't do technical analysis.

Technical analysis involves prediction based on price and volume data. Most quants strongly believe that predicting the market based on price and volume data is impossible. None of the business models mentionned below involve any prediction of future prices. The only claims we make about the future are about probability distributions.

 Quants build multifactor models based on (mostly) fundamental data. Write and price derivatives. Make markets at high frequencies. Buy and sell securities and portfolios that are stationary relative to one another. And beg, borrow, buy, or steal your data in order to predict what you or funds are going to do. 

### Multifactor models

This is the bread-and-butter for quant funds. AQR has pioneered this space the most.

Multifactor models are models designed to extract cross-sectional risk premia in markets. Put simply you look at all the stocks in a market. Rank them based on some metric(s). Long the top decile. Short the bottom decile. If that market-neutral portfolio outperforms on a consistent basis then well done! You have found a risk premium.

Classical and well known risk premia include:

    Momentum - stocks that moon continue to moon.
    Size - small caps tend to outperform large caps.
    Value - high-value stocks tend to outperform low-value stocks.
    Mean Reversion - some securities are stationary e.g. volatility.
    Quality - quality stocks tend to outperform low quality stocks.
    Low Volatility - low vol stocks tend to outperform on a risk-adjusted basis.
    Aggressiveness - conservative companies tend to outperform aggressive companies.

Some of these factors used to work but no longer do because the mere fact that so many quant funds discovered them caused the alpha in them to decay. Most quants I know are looking into more alternative factors using machine learning based on sentiment, web-traffic, social media mentions, etc. I'll elaborate further down.

Book Recommendation: Quantitative Equity Portfolio Management by Ludwig B Chincarini

### Writing and Pricing Derivatives

This is another bread-and-butter for quant funds. It used to be a lot bigger before 2008 when the street had more appetite for exotics. But it's still good business. It was pioneered by quants like Ed Thorpe. You should definitely read his book the man was friends with Claude Shannon ffs - A Man For All Markets by Edward O. Thorp.

Writing and pricing derivatives involves six easy steps.

    Create a model that can output synthetic prices and has parameters you can tune.
    Fit the model to a stock or portfolio such that it produces synthetic prices that have the same statistical characteristics of the underlying stock or portfolio.
    Sample tens of thousands of possible future market scenarios in a Monte Carlo simulation.
    Compute the payoff of the derivative in each scenario.
    Discount the future values to determine the expected value of the option.
    Pad the price to take into account counterparty, model, and specification risks.

Now for vanilla options you can do this on a calculator using analytical methods. But for portfolios of assets or complex derivatives with nonlinear payoff structures you often need to build a pricing model yourself. This is what I used to get paid to do for big corporates looking to hedge things like generators for power plants.

What kinds of models are used here? Stochastic processes or (maybe) generative machine learning models.

Book Recommendation #1: Options, Futures, and Other Derivatives by John C. Hull

Book Recommendation #2: Monte Carlo Methods in Financial Engineering by Paul Glasserman

### Market Making and Latency Arbitrage

This is what the big funds like Citadel, Jane Street, Two Sigma, etc. are doing. Full disclaimer I've never worked on the HFT side of things but I'll explain it the way I understand it. Comment if you want to add or correct.

High Frequency Trading firms like Citadel, Jane Street, and Two Sigma get paid by exchanges by provide market liquidity. They are market makers always ready to buy or sell whatever share you or a large institutional fund needs to trade. They make money by placing a limit order to sell or a buy limit order in order to earn the bid-ask spread.

Latency arbitrage is when HFT firms buy and sell the same security at the same time in different markets because two or more exchanges are displaying a different price for that security. For example, if a whale pushes the price of a security high on the New York Stock Exchange then an HFT firm might sell the security on the NYSE at the same time as they buy it on the Chicago Stock Exchange and profit the spread between the two exchanges.

Book Recommendation #1: Trading and Exchanges by Larry Harris

Book Recommendation #2: High Frequency Trading by Irene Aldridge

Book Recommendation #3: Flash Boys by Michael Lewis - this one has pretty mixed reviews amongst the quants I know (some of whom do this stuff for a living). Ken Griffin even called it a "work of fiction". But it is a great story and regardless of the plot the technology and infrastructure used for HFT is accurately portrayed.

### Statistical Arbitrage

This has gone pretty mainstream. I'm sure most of you have heard of pairs trading but it is certainly another staple for quant funds. And if you read The Man Who Solved The Market about RenTech (the most famous quant fund in the world) they allude to doing something similar with basket options. Nobody knows how true that is.

Statistical arbitrage involves identifying securities that should behave similarly and going long the one which is relatively undervalued and short the one which is relatively overvalued. In the simplest case you might say that Coca-Cola and Pepsi are a pair and go long/short them when depending on how they are priced relative to one another.

In a more complex trade you might go long off-the-run treasuries and short on-the-run treasuries because older identical treasuries sell at a discount to those hot off of the money printer. This is the trade that caused the famous LTCM crash. What happened is Russia defaulted on its debt and the demand for on-the-run treasuries skyrocketed. LTCM was short on-the-run treasuries and got squeezed. Their models told them to double down multiple times (martingale) but the distortion continued beyond the point where they could borrow money to finance the trade. So they went insolvent and the Federal Reserve stepped in to do a bail out. This all happened in 1998!

The LTCM example might not qualify as "statistical" arbitrage since the securities are identical so it is literally arbitrage ... but the risk models are statistical and use the same techniques as we use when writing and pricing derivatives.

Book Recommendation #1: Algorithmic Trading: Winning Strategies and Their Rationale by Ernie Chan

Book Recommendation #2: When Genius Failed by Roger Lowenstein

### Information Arbitrage

The most modern reincarnation of quantitative finance involves identifying information arbitrage opportunities with alternative data. Alternative data is any data that is not price data or fundamental data. Large audio, text, document, video, click stream, etc. datasets are all examples of alternative datasets that could power information arbitrage.

Here are some strategies I have seen or heard of being used,

    Using natural language processing algorithms to read tens of thousands of news articles a day to track sentiment, named entities mentioned, events, etc. This is pretty well known.
    Using high resolution satellite data to (1) track ships coming in and out of ports, (2) count cars in Walmart / Target parking lots to estimate revenues, (3) estimating the amount of oil in middle eastern oil reserves based on the shadow cast on the structure. This is the kind of analysis built by Orbital Insights.
    Using meteorological models to predict when the monsoon season will hit and how extreme it will be and what the impact will be on certain crops like sugar which are very sensitive to it.
    Using temperature monitors in European rivers to predict demand for natural gas and heating oil. I heard from a quant that at a certain °F nuclear power plants can't use river water for cooling so they slow down causing a spike in demand for gas ... not sure how true that is but it's an example of information arbitrage.
    Using flight path information to predict mergers and acquisitions between major companies.
    Using web-traffic data from SimilarWeb to predict which online retailers or hotel chains are most likely to have the best earnings this quarter.
    Using click stream data from Robinhood to predict what meme stock is going to be the next pump and dump on r/wallstreetbets. You all know that this is a thing right haha ;-).

Not a lot of good books on this topic yet but I've heard that The Book of Alternative Data by Alexander Denev does a half decent job. You'll probably find more ideas browsing parts of Reddit though like /r/datasets.