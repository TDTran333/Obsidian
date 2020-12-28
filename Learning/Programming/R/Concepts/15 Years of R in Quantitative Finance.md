---
tags: R, finance
---
Link: [YouTube](https://www.youtube.com/watch?v=3sroV_RltQA)

# 15 Years of R in Quantitative Finance
> Better data analysis requires reproducibility and scalability.

### Using R to do better analysis (Spend more time analysing instead of manipulating data)

Good analysis depends on sound data.
Reported data is formatted for printing, not for processing.
How do we scale the analysis?
Tables are useful but visualizations are better.

The Excel process:
1. Gather the data in a single tab
2. Create a plot referencing the group totals
3. Customize the plot

How do we answers new questions with our excel process? 
In Excel, we'd have to rework the entire process

The Excel process seems fragile, requires alot of repetition and is prone to errors

The R process:

```R
data_file %>%
	prepare_market_data() %>%
	collect_groups() %>%
	plot_groups()
```

Better analysis with R
* Reliable
* Replicable & Efficient
* Robust to future change

### Build models that you can't buy on marketplace

Build on Shiny for portfolio holdings and stock analysis
Custom-made for firm's needs

### Q&A
Exciting new packages?
List-columns vs. multiple tables
Changes to format changes from data files
Delivering data to non-r users
Design of the shiny dashboard vs. flex dashboard

