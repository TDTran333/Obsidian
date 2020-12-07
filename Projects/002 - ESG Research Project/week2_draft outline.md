Notes and criterias for research project @ [[Guide projet supervisé]]
Document version: 0.3

---
# TO DO TODAY
### [[FDR Critics]]
### [[green vs. brown literature]]
### INVESTIGATION DES DONNÉES
### LT TARGET IS A SYNTHETISED 4 PAGE ARTICLE

#### Notes à moi même suivant les appels
Plus de détails, être plus précis avec le sujet

###### Vérifier les références et travaux récentes sur le sujet
#### List of [[Top Finance Journals]]
#######  Investiguer green vs. brown et performance comparative

Literature ESG
Litérature peer performance

###### On veut le screening plot
Distinctiveness de green vs. brown
Faire le graphique de peerperformance package

Exemple de screenplot
![[Pasted image 20201118020833.png]]


##### Répondre à la critique du FDR et la contre critique
Être en mesure de bien l'expliquer

##### Indiquer pourquoi on utilise le FDR
Alternatives au FDR de Storey?
Important à savoir

Définition des greens vs. browns
Dépend de l'industrie
Car certain industrie ont des corrélations  très élevé

Important que les statistiques de test ne soit pas corrélé quand on regarde les industries
Vérifier la corrélation
**À revoir**
S'assurer que les données soient indépendantes, regarder la corrélation des alphas

Measure peer performance...
D'autre mesure de performance?
Il en a 3 dans l'article principal

Univers ESG, c'est quoi
Performance dans l'univers ESG
Modèle inconditionnel utilisant le ratio sharpe et
Modèle conditionnel utilisant des facteurs

Description base de données
Description méthodologie

Bibliographie à voir à la toute fin
Pis overleaf pour les formules

# Draft research document

## GOAL of this research project:
After initial discussions, we wanted to write an article for either R journal or a finance journal and there is two possible focus that have emerged:

* **Focus A** is about the peerperformance package in particular. Created by Ardia and Boudt (started 2012, updated until 2018), it is a R package that allows peer performance comparison controlling for luck based on Storey's (2002) false discoveries rate model as described by Barras et. al (2010) in their application in finance on mutual funds. We would review and update the R package. We would then illustrate the tool by using for example the relative performance of green firms vs. brown firms and present it in a R *vignette* (a long-form guide to the R package) . 

* **Focus B** flip the subject over and focus on the topic of ESG and in particular the Environment pillar for public equities as proxied by the S&P 500 and wonder if there is any significant difference in term of performance in regards to green firms vs. brown firms controlling for other markets factors (ex: Fama-French, Cahart, Fung & Hsieh), for industries and ESG ratings. We would use the peerperformance package to minimize the impact of type 1 errors and try to provide an answer as well as generate portfolios and test the performance out of sample of the green portfolios.

Currently, focus B seems to be more challenging but does provide a more exciting output and tries to answer a question of interest for the investment community in regards to the recent trend of ESG investing. We would lean toward focus B.

## QUESTIONS 
* Is there a significant return difference between green vs. brown firms?
	* [[green vs. brown]]
* Has it changed over time? 
* How can we use that information to select managers? To select stocks?
* What is ESG?
	* ESG investing (also known as sustainable or socially responsible investing SRI) 
* How do we measure ESG?
* What is a [[Green firms]]?
* What is a [[Brown firms]]?
* How did ESG change over time?
* How do we compare peer performance?
* What are the key measures?
* Is there any new models?
* What have been done in the space recently?
* How does the peerperformance package work?
* What is the methodology?
* What are the models used?
* What is false discovery rate?
* Where did it come from?
* What is HAC residuals?
* What are the main papers in the literature?
	* In term of peer performance?
	* In term of ESG performance?
* What data should we use?
* Who will provide the data?
* What are the characterstics of the data?
* What time period does it cover?
* How was it generated?
* What are some example of scientific paper?
* How interesting is the topic at hand?
* How to update an R package?
* How to document an R package?
* How to test a R package?
* How to publish a R package?
* How to write a R vignette?
* 

## STRUCTURE of document
#### Abstract

Keywords: False discoveries, peer performance, performance measurement, ESG, screening alpha

#### Introduction

Our work is based on the paper from [[Ardia_Boudt_2018_The_peer_performance_ratios_of_hedge_funds]].

They discuss about applying a methodology from [[Barras_Scaillet_Wermers_2010_False_Discoveries_in_Mutual_Fund_Performance]].

That methodology has been attacked in 2019 by two greek researchers [[Andrikogiannopoulou_Papakonstantinou_2019_Reassessing_False_Discoveries_in_Mutual_Fund_Performance]]. 

In which Barras et. al replied : [[Barras_Scaillet_Wermers_2019_Reassessing_False_Discoveries_in_Mutual_Fund_Performance_a_reply]].

Am I convinced by their arguments?

Then I need to follow-up with the innovation part of the project.

We want to present ESG peer performance of [[Green firms | green firms]] vs. [[Brown firms | brown firms]].


* What are we going to show?
* How did we do it?
* What are the key results?
* How are the sections structured?

#### Body
##### Literature

##### Methodology
[[False Rate Discovery]]
[[Ardia_Boudt_2018_The_peer_performance_ratios_of_hedge_funds]]

##### Data

Our empirical study focuses on S&P 500 firms for a period ranging from January 2010 to June 2018. To quantify a firm's greenness, we rely on the ASSET4/Refinitiv CO2 (carbon dioxide) equivalent greenhouse gas (GHG) emissions data scaled by the firms' revenue. Thus, the variable measures the number of tonnes of CO2 equivalent GHG emissions necessary for a firm to generate a one million dollar revenue, namely, the GHG emissions intensity. Firms whose variable is below (above) the 25th (75th) percentile on a given day are defined as green (brown) firms.
Refinitiv ESG data cover 80% of global market cap across 76 countries, with 450 ESG metrics including scores and grades going back to 2002.
 
![[Pasted image 20201113155510.png]]
![[Pasted image 20201113155506.png]]

##### Key results and charts discussion
Insert screenplot of green vs. brown

#### Conclusion
* What did we show?
* What can we expand on?
* What’s next?

## Related PAPERS

[[Ardia_Boudt_2018_The_peer_performance_ratios_of_hedge_funds]]
[[Pastor_Stambaugh_Taylor_2020_Sustainable_Investing_in_Equilibrium]]
[[Barras_Scaillet_Wermers_2010_False_Discoveries_in_Mutual_Fund_Performance]]
[[Barras_Scaillet_Wermers_2019_Reassessing_False_Discoveries_in_Mutual_Fund_Performance_a_reply]]


Sermpinis, Georgios, Arman Hassanniakalager, Charalampos Stasinakis, and Ioannis Psaradellis. “Technical Analysis and Discrete False Discovery Rate: Evidence from MSCI Indices.” SSRN Electronic Journal, 2018. https://doi.org/10.2139/ssrn.3284621.

[[Sermpinis_Hassanniakalager_Stasinakis_Psaradellis_2018_Technical_Analysis_and_Discrete_False_Discovery_Rate]]

Lee, Yongjae, Do-Gyun Kwon, Woo Chang Kim, and Frank J. Fabozzi. “An Alternative Approach for Portfolio Performance Evaluation: Enabling Fund Evaluation Relative to Peer Group via Malkiel’s Monkey.” Applied Economics 50, no. 40 (August 27, 2018): 4318–27. https://doi.org/10.1080/00036846.2018.1444263.


 
PAPER 3 summary
A direct approach to false discovery rates (2002)
https://www.jstor.org/stable/3088784?seq=1
Authors: John D. Storey
Abstract: 
Multiple-hypothesis testing involves guarding against much more complicated errors than single-hypothesis testing. Whereas we typically control the type I error rate for a single-hypothesis test, a compound error rate is controlled for multiple-hypothesis tests. For example, controlling the false discovery rate FDR traditionally involves intricate sequential p-value rejection methods based on the observed data. Whereas a sequential p-value method fixes the error rate and estimates its corresponding rejection region, we propose the opposite approach—we fix the rejection region and then estimate its corresponding error rate. This new approach offers increased applicability, accuracy and power. We apply the methodology to both the positive false discovery rate pFDR and FDR, and provide evidence for its benefits. It is shown that pFDR is probably the quantity of interest over FDR. Also discussed is the calculation of the q-value, the pFDR analogue of the p-value, which eliminates the need to set the error rate beforehand as is traditionally done. Some simple numerical examples are presented that show that this new approach can yield an increase of over eight times in power compared with the Benjamini-Hochberg FDR method. 
Keywords: False discovery rate, Multiple comparisons, Positive false discovery rate; p-values,
q-values, Sequential p-value methods, Simultaneous inference

 
PAPER 4 summary
Reassessing False Discoveries in Mutual Fund Performance: Skill, Luck, or Lack of Power? A Reply (2019)
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3439231
Authors: Laurent Barras, Olivier Scaillet, and Russ Wermers
Abstract: 
Andrikogiannopoulou and Papakonstantinou (AP; 2019) conduct an inquiry into the bias of the False Discovery Rate (FDR) estimators of Barras, Scaillet, and Wermers (BSW; 2010). In this Reply, we replicate their results, then further explore the bias issue by (i) using different parameter values, and (ii) updating the sample period. Over the original period (1975-2006), we show how reasonable adjustments to the parameter choices made by BSW and AP results in a sizeable reduction in the bias relative to AP. Over the updated period (1975-2018), we further show that the performance of the FDR improves dramatically across a large range of parameter values. Specifically, we find that the probability of misclassifying a fund with a true alpha of 2% per year is 32% (versus 65% in AP). Our results, in combination with those of AP, indicate that the use of the FDR in finance should be accompanied by a careful evaluation of the underlying data generating process, especially when the sample size is small. 
Keywords: False Discovery Rate, Multiple Testing, Mutual Fund Performance

 
PAPER 5 summary
Climate change concerns and the performance of green versus brown stocks (2020)
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3717722
Authors: David Ardia, Keven Bluteau, Kris Boudtb, Koen Inghelbrecht
Abstract: 
We empirically test the prediction of Pastor, Stambaugh, and Taylor 2020 that green firms can outperform brown firms when climate change concerns strengthen unexpectedly for S&P 500 companies over the period January 2010 - June 2018. To capture unexpected increases in climate change concerns, we construct a Media Climate Change Concern index using climate change-related news published by major U.S. newspapers. We find a negative relationship between the firms' exposure to the Media Climate Change Concerns index and the level of the firm's greenhouse gas emission per unit of revenue. This result implies that when concerns about climate change rise unexpectedly, green firms' stock price increases, while brown firms' stock price decreases. Further, using topic modeling, we analyze which type of climate change news drives this relationship. We identify five themes that have an effect on green vs. brown stock returns. Some of those themes can be related to change in investors' expectations about the future cash-flow of green vs. brown firms, while others cannot. This result implies that the relationship between concern and green vs. brown stock returns arises from both investors updating their expectations about the future cash-flows of green and brown firms and changes in investors' sustainability taste.
Keywords: Asset Pricing, Climate Change, Sustainable Investing, ESG, Greenhouse Gas Emission, Sentometrics, Textual Analysis
Related articles to read: 
Sustainable investments:
Sustainable Investing in Equilibrium
Lubos Pastor, Robert F. Stambaugh, Lucian A. Taylor		
Key results:
When looking at the green (brown) portfolio returns individually, we _nd a positive (negative) and significant relationship with the MCCC index. This relationship is stronger, in absolute terms, for the brown portfolio than for the green portfolio. Thus, in case of an unexpected increase in climate change concerns, investors tend to penalize more harshly brown firms than they reward green firms, on average.
Moreover, we find that stock returns have a positive relationship with the level of GHG emissions intensity. This result suggests that brown firms outperform green firms in the absence of unexpected increases in climate change concern. 
PAPER 6 summary
Sustainable Investing in Equilibrium (2020)
https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3498354
Authors: Lubos Pastor, Robert F. Stambaugh, Lucian A. Taylor
Abstract: 
We model investing that considers environmental, social, and governance (ESG) criteria. In equilibrium, green assets have low expected returns because investors enjoy holding them and because green assets hedge climate risk. Green assets nevertheless outperform when positive shocks hit the ESG factor, which captures shifts in customers' tastes for green products and investors' tastes for green holdings. The ESG factor and the market portfolio price assets in a two-factor model. The ESG investment industry is largest when investors' ESG preferences differ most. Sustainable investing produces positive social impact by making firms greener and by shifting real investment toward green firms. 
Keywords: sustainable investing, socially responsible investing, ESG, social impact
Related articles to read: 
Sustainable investments:
Sustainable Investing in Equilibrium
Lubos Pastor, Robert F. Stambaugh, Lucian A. Taylor	
Key results:
We show that agents' tastes for green holdings affect asset prices. Agents are willing to pay more for greener firms, thereby lowering the firms' costs of capital. Green assets have negative CAPM alphas, whereas brown assets have positive alphas. Consequently, agents with stronger ESG preferences, whose portfolios tilt more toward green assets and away from brown assets, earn lower expected returns. Yet such agents are not unhappy because they derive utility from their holdings.
We define the “ESG factor" as a scaled return on the ESG portfolio. A simple version of the ESG factor is a green-minus-brown portfolio return, where both green and brown portfolios are weighted by ESG characteristics.
Our model implies that sustainable investing leads to positive social impact.
Finally, we extend the model by allowing climate to enter investors' utility. Evidence suggests that brown assets have higher climate betas than green assets (e.g., Choi, Gao, and Jiang, 2019; Engle et al., 2020).
The model clearly predicts that green assets underperform brown over a sufficiently long period - a period long enough so that unexpected changes in ESG tastes average to zero.
Related articles to read: 
Sustainable investments:
The Effect of Socially Responsible Investing on Portfolio Performance (2007)
Alexander Kempf, Peer Osthoff

 
PAPER 7 summary
The effect of socially responsible investing on portfolio performance (2007)
https://www.econstor.eu/bitstream/10419/57725/1/702962686.pdf
Authors: 
Abstract: 
More and more investors apply socially responsible screens when building their stock portfolios.  This raises the question whether these investors can increase their performance by incorporating such screens into their investment process.  To answer this question, we implement a simple trading strategy based on socially responsible ratings from the KLD Research & Analytics:  Buy stocks with high socially responsible ratings and sell stocks with low socially responsible ratings.  We find that this strategy leads to high abnormal returns of up to 8.7% per year.   The maximum abnormal returns are reached when investors employ the best-in-class screening approach, use a combination of several socially responsible screens at the same time, and restrict themselves to stocks with extreme socially responsible ratings. The abnormal returns re-main significant even after taking into account reasonable transaction costs.
Keywords: Socially Responsible Investing, Portfolio Management, Trading Strategy 
PeerPerformance R package Summary
https://cran.r-project.org/web/packages/PeerPerformance/index.html
Github: https://github.com/ArdiaD/PeerPerformance
Description
PeerPerformance (Ardia and Boudt, 20xx) is an R package for the peer-performance evaluation of financial investments with luck-correction, useful in the financial industry. In particular, it implements the peer performance ratios of Ardia and Boudt (2018) which measure the percentage of peers a focal (hedge) fund outperforms and underperforms, after correction for luck. It is useful for fund or portfolio managers to benchmark their investments or screen a universe of new funds. In addition, the package implements the testing framework for the Sharpe and modified Sharpe ratios, described in Ledoit and Wolf (2008) and Ardia and Boudt (2015).
Functions
Sharpe ratio: 
sharpe : Compute Sharpe ratio
sharpeTesting: Testing the difference of Sharpe ratios
sharpeScreening: Screening using the Sharpe outperformance ratio
Modified Share ratio: 
msharpe: Compute modified Sharpe ratio
msharpeTesting: Screening using the modified Sharpe outperformance ratio
msharpeScreening: Testing the difference of modified Sharpe ratios
Screening function: 
alphaScreening: Screening using the alpha outperformance ratio
sharpeScreening: Screening using the Sharpe outperformance ratio
msharpeScreening: Testing the difference of modified Sharpe ratios
Hfdata: Hedge fund data
 
Building R Packages in RStudio
 	








devtools::use_package()
devtools::load_all()
usethis::use_testthat() devtools::test()
devtools::document()
usethis::use_vignette()
usethis::use_data()
@export @import

Tutorial / Screencast by David Robinson: https://www.youtube.com/watch?v=F4oUJp76KUY
The process of creating R package includes:
Filling out the DESCRIPTION file
Creating datasets with a script in data-raw and saving them to data
Documenting the datasets with Roxygen2 and devtools::document()
Publishing to GitHub
 
 
Roxygen2 package to generate R documentation
https://cran.r-project.org/web/packages/roxygen2/vignettes/roxygen2.html
Add roxygen comments to source file. 
roxygen2::roxygenise() converts roxygen comments to .Rd files. 
R converts.Rd files to human readable documentation. 
Object documentation: https://r-pkgs.org/man.html
Vignettes: long-form documentation: https://r-pkgs.org/vignettes.html
See https://r-pkgs.org/ for complete documentation
 
Documenting datasets
@format gives an overview of the dataset. For data frames, you should include a definition list that describes each variable. It’s usually a good idea to describe variables’ units here.
@source provides details of where you got the data, often a \url{}.
Example:
#' @format A data frame with 53940 rows and 10 variables:
#' \describe{
#'   \item{price}{price, in US dollars}
#'   \item{carat}{weight of the diamond, in carats}
#'   ...
#' }
#' @source \url{http://www.diamondse.info/}

Documenting functions
Most functions have three tags: @param, @examples and @return. 
All the roxygen lines preceding a function are called a block.
Blocks are broken up into tags
Roxygen2 comments start with #' and come before a function. 
The first sentence becomes the title of the documentation.
The second paragraph is the description
The third and subsequent paragraphs go into the details
@seealso allows you to point to other useful resources 

 




