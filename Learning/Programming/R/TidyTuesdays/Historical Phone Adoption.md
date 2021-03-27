---
aliases: TidyTuesday - Historical Phone Adoption
tags: R, tidytuesday
---
Links: [Screencast](https://www.youtube.com/watch?v=pJPqAIb8MKA), [Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#historical-phones), [Data](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-11-10/readme.md)

# TidyTuesday - Historical Phone Adoption
## Topic: Joining tables, Animated world choropleth, Adding IQR to geom_line, World development indicators package

### Data
###### mobile.csv & landline.csv
| variable    | class     | description                                         |
|:----------- |:--------- |:--------------------------------------------------- |
| entity      | character | Country                                             |
| code        | character | Country code                                        |
| year        | double    | Year                                                |
| total_pop   | double    | Gapminder total population                          |
| gdp_per_cap | double    | GDP per capita, PPP (constant 2011 international $) |
| mobile_subs | double    | Fixed mobile subscriptions (per 100 people)         |
| continent   | character | Continent                                           |

### Annotations
| Time    | Description                                                                                                                                                                          |
| ------- |:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 2:15    | Use bind_rows from the dplyr package to combine the two data sets.                                                                                                                   |
| 7:30    | Use group = interaction(type, country) within ggplot aes() to set the interaction type with every single country on one plot.                                                        |
| 9:30    | Use semi_join from the dplyr package to join rows from phones with a match in country_sizes.                                                                                         |
| 14:00   | Use quantile from the stats package within summarize to show the 25th, and 75th quantiles (interquartile range) on the plot.                                                         |
| 17:50   | Import the wdi package (World Development Indicators from the World Bank) with extra = TRUE in order to get the iso3c code and income level for each country.                        |
| 19:45   | Use inner_join from the dplyr package to join the WDI data with the phones data.                                                                                                     |
| 20:35   | Use fct_relevel from the forcats package to reorder income factor levels in ascending order.                                                                                         |
| 21:05   | Create an anonymous function using . (dot).                                                                                                                                          |
| 29:30   | Use inner_join from the dplyr package to join the mobile data and landline data together with a geom_abline to see how different the total populations are between the two datasets. |
| 31:00   | Use geom_hline to add a refrence line to the plot shwoing when each country crossed the 50 per 100 subscription mark.                                                                |
| 35:20   | Use summarize from the dplyr package with min(year([Mobile >= 50])) to find the year in which each country crossed the 50 per 100 subscription mark.                                 |
| 35:20   | Use summarize from the dplyr package with max(Mobile) to find the peak number of mobile subscriptions per country.                                                                   |
| 35:20   | Use na_if from the dplyr package within summarize to change Inf to NA.                                                                                                               |
| 38:20   | Using the WDIsearch function to search the WDI package for proper GDP per capita indicator. Ended up using the NY.GDP.PCAP.PP.KD indicator.                                          |
| 39:05   | Adding the GDP data from the WDI package to the country_incomes table.                                                                                                               |
| 39:52   | Using the inner_join function from the dplyr package to join the phones table with the country_incomes table pulling in the gdp_per_capita variable.                                 |
| 42:25   | Using the WDIsearch function to search the WDI package for proper population indicator. Ended up using the SP.POP.TOTL indicator.                                                    |
| 50:00   | Create an animated choropleth world map with fill = subscriptions.                                                                                                                   |
| 1:00:00 | Summary of screencast                                                                                                                                                                |
