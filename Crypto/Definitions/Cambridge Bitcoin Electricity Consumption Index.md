---
aliases:
tags: bitcoin
---
Link: [Website](https://cbeci.org/), [Methodology](https://cbeci.org/cbeci/methodology), [Comparison](https://cbeci.org/cbeci/comparisons)

# Cambridge Bitcoin Electricity Consumption Index

### Summary

The Cambridge Bitcoin Electricity Consumption Index (CBECI) provides a real-time estimate of the total electricity load and consumption of the Bitcoin network. The model is based on a bottom-up approach initially developed by [Marc Bevand](http://blog.zorinaq.com/bitcoin-electricity-consumption/) in 2017 that takes different types of available mining hardware as the starting point.

Given that the exact electricity consumption cannot be determined, the CBECI provides a range of possibilities consisting of a **lower bound** (floor) and an **upper bound** (ceiling) estimate. Within the boundaries of this range, a **best-guess** estimate is calculated to provide a more realistic figure that we believe comes closest to Bitcoin’s real annual electricity consumption.

The lower bound estimate corresponds to the absolute minimum total electricity expenditure based on the best case assumption that all miners always use the most energy-efficient equipment available on the market. The upper bound estimate specifies the absolute maximum total electricity expenditure based on the worst case assumption that all miners always use the least energy-efficient hardware available on the market as long as running the equipment is still profitable in electricity terms. The best-guess estimate is based on the assumption that miners use a basket of profitable hardware rather than a single model.

### Representation

The CBECI landing page displays two numbers for each type of estimate.

The first number refers to the total **electrical power** consumed by the Bitcoin network and is expressed in gigawatts (GW). This figure is updated every 30 seconds and corresponds to the rate at which Bitcoin uses electricity.

The second number refers to the total **yearly electricity consumption** of the Bitcoin network and is expressed in terawatt-hours (TWh). We annualise Bitcoin’s electricity consumption assuming continuous power usage at the aforementioned rate over the period of one year. We apply a **7-day moving average** to the resulting data point in order to make the output value less dependent of short-term hashrate movements, and thus more suitable for comparisons with alternative uses of electricity.