---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=h29g21z0a68), Part 2

# ggplot2 Workshop

### The Grammar of Graphics

The grammar of graphics book (Leland Wilkinson)
* A theoretical deconstruction of data graphics
	* Not interested in the why
	* Not interested in beauty
	* Not interested in algorithms
	* Very interested in how to design the system that allows all that

#### Central Idea: What is Graphics? Decompose graphics into its constituents
* Theme
* Coordinates
* Facets
* Geometries
* Scales
* Statististics
* Mapping
* Data

#### The grammar of graphics is the theory of the structure of graphics
##### Data
* Data is not just data.
* Representation defines what can be done with it.
* Grammar requires a tidy format (though it precedes the notion).

##### Mapping
* Allow generic datasets to be understood by the graphic system.
* Aesthetic mapping: Link variables in data to graphical properties in the geometry.
* Facet mapping: Link variables in the data to panels in the facet layout.

##### Statistics
* Even though data is tidy, it may not represent the displayed values.
* Transform input variables to displayed values:
	* Count number of observations in each category for a bar chart.
	* Calculate summary statistics for a boxplot.
* Is implicit in many plot-types but can often be done prior to plotting.

##### Scales
* Most data does not directly represent graphical properties.
* A scale translate back and forth between variable ranges and property ranges
	* Categories -> Color
	* Numbers -> Position
	* ...
* Imply a specific interpretation of values;  discrete, continuous, etc.

##### Geometries
* How to interpret aesthetics as graphical representations.
* It a progression of positional aesthetics a number of points, a line, a single polygon or something else entirely?
* To a high degree the determinator of your plot type.

##### Facets
* Define the number of panels with equal logic and split data among them.
* Small multiples
	* Allows you to look at small subsets of your data in separate plots
* Panel layout may carry meaning 

##### Coordinates
* Positional aesthetics are special.
	* Variables are mapped, scaled, applied to a geometry
	* But in the end, the position values are interpreted by a coordinate system
* Defines the physical mapping of the aesthetics to the paper
* Vaguely similar to color profile mapping for color aesthetics

##### Theme
* None of the priors talked about the visual look of the plot.
* Theming spans every part of the graphic that is not linked to data.

### The ggplot2 API
* Grammar of Graphics is a design system
* ggplot2 is an implementation
* Hadley's grammar != Leland's grammar
* The spirit lives on
* Other implementations:
	* Tableau
	* Vega-Lite

#### General
* If an aesthetic is linked to data it is put into `aes()`
* If you simple want to set it to a value, put it outside of `aes()`
* geoms are drawn in the order they are added.

#### Statistics
* Linked to geometries
* Every geom has a default statistic
* A layer can be created with a call to stat_\*() or geom_\*(), but community has coalesced around geom_\*()
* If you have precomputed data use identity stat
* Use after_stat() to modify mapping from stats

##### after_stat()
Control aesthetic evaluation.
Use the after_stat() function to flag that evaluation of the aesthetic mapping should be postponed until after stat transformation. Similarly, you should use after_scale() to flag evaluation of mapping for after data has been scaled. 

#### Scales

### Beyond ggplot2

### Drawing anything

1:26/2:28