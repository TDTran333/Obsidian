CRAN:  https://cran.r-project.org/web/packages/PeerPerformance/index.html
Github: https://github.com/ArdiaD/PeerPerformance
Documentation: ![[PeerPerformance_CRAN.pdf]]

# PeerPerformance: Luck-corrected peer performance analysis in R

### Description
PeerPerformance (Ardia and Boudt, 20xx) is an R package for the peer-performance evaluation of financial investments with luck-correction, useful in the financial industry. In particular, it implements the [[week5_notes using PeerPerformance R Package]] of [[Ardia_Boudt_2018_The_peer_performance_ratios_of_hedge_funds | Ardia and Boudt (2018)]] which measure the percentage of peers a focal (hedge) fund outperforms and underperforms, after correction for luck. It is useful for fund or portfolio managers to benchmark their investments or screen a universe of new funds. In addition, the package implements the testing framework for the Sharpe and modified Sharpe ratios, described in Ledoit and Wolf (2008) and Ardia and Boudt (2015).

### Functions
##### Sharpe ratio: 
•	[[PeerPerformance - sharpe|sharpe]] : Compute Sharpe ratio
•	[[PeerPerformance - sharpeTesting|sharpeTesting]]: Testing the difference of Sharpe ratios
•	[[PeerPerformance - sharpeTesting|sharpeScreening]]: Screening using the Sharpe outperformance ratio

##### Modified Share ratio: 
•	[[PeerPerformance - msharpe|msharpe]]: Compute modified Sharpe ratio
•	[[PeerPerformance - msharpeTesting|msharpeTesting]]: Screening using the modified Sharpe outperformance ratio
•	[[PeerPerformance- msharpeScreening|msharpeScreening]]: Testing the difference of modified Sharpe ratios

##### Screening function: 
•	[[PeerPerformance - alphaScreening | alphaScreening]]: Screening using the alpha outperformance ratio
•	[[PeerPerformance - sharpeScreening | sharpeScreening]]: Screening using the Sharpe outperformance ratio
•	[[PeerPerformance- msharpeScreening | msharpeScreening]]: Testing the difference of modified Sharpe ratios

##### Hfdata: 
• [[PeerPerformance - Hedge fund data]]
