Title: Tidy Tuesday live screencast: Analyzing historical phones in R
Link: [Screencast](https://www.youtube.com/watch?v=pJPqAIb8MKA)| [TidyTuesday](https://github.com/rfordatascience/tidytuesday/blob/master/data/2020/2020-11-10/readme.md)
Content creator: David Robinson
Dataset: Historical phone adoption
Tags: #R | #TidyTuesday

---

### Notable topics
* Joining tables
* Animated world [[Choropleth Map | chrolopleth]]
* Adding IQR to geom_line
* World development indicators package

### Summary of the screencast
Combined mobile and landline data
What time did mobile take off
Progression over time of landline and Mobile
Data quality checking
Summarizing among countries

### Specific tricks, tips and tools
[Timestamps & Annotations](https://github.com/dgrtwo/data-screencasts/tree/master/screencast-annotations#historical-phones)

### Dataset]
> Hannah Ritchie (2017) - "Technology Adoption". Published online at OurWorldInData.org. Retrieved from: https://ourworldindata.org/technology-adoption [Online Resource]

###### mobile.csv & landline.csv
| variable | class | description |
|:-|:-|:-|
| entity | character | Country |
| code | character | Country code |
| year | double | Year |
| total_pop | double | Gapminder total population |
| gdp_per_cap | double | GDP per capita, PPP (constant 2011 international $) |
| mobile_subs | double | Fixed mobile subscriptions (per 100 people) |
| continent | character | Continent |
