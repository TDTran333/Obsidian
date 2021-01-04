---
aliases: shiny css
tags: R, shiny
---
Link: [YouTube](https://www.youtube.com/watch?v=GHBwprI_Py4)

# Styling Shiny apps

### The state of Shiny styling
1. I'm just happy that it works: Just accepts the defaults
2. I want it punched up a bit: Uses shinythemes
3. I want it to look a lot different: Uses alternate Shiny UI toolkit like shinydashboard, shinymaterial, Rinterface
4. I want specific fonts/colors/styles: Writes lots of custom CSS to modify Bootstrap
5. Native HTML: Writes custom HTML/CSS using HTML template

### Shiny's default UI is powered by Bootstrap
* An open source CSS framework, originaly started at Twitter
* Now top 10 project on GitHub by stars, used by millions of websites
* Designed to be easily customized...by web designers

### Sass is a better way to write CSS
Sass hs the ability to declare and use variables
Browser don't understand Sass
Have to use Sass compiler
We want to be able to adjust it from R.

### Two new R packages
sass - Compile Sass to CSS from R
bootstraplib - Customize and use Bootstrap from R based on the sass package

### The bootstraplib package - now known as bslib
* R bindinds for Bootstrap
* Designed to be used from Shiny apps, R Markdownm HTML widget packages and anywhere else Bootstrap might be needed
* Customize and re-customize Bootstrap with your own variables and rules, straight from R.
* Built-in support for bootswatch (i.e. shinythemes), which can also be combined with your own customizations

### Which variables should I change?
Tools for configuring Bootstrap are only useful if you can figoure out which variables to configure.

[Bootstrap 3 variable list](https://bit.ly/bs3-sass-vars)
[Bootstrap 4 variable list](https://bit.ly/bs4-sass-vars)
[bootstraplib docs](https://rstudio.github.io/bslib/)

run_with_themer() generate an UI and source codes
shinyOptions(plot.autocolor = TRUE) for dark theme plots built into Shiny

### Plot theming
* Statis plots (plotOutput) don't respect CSS styles
* Add shinyOptions(plot.autocolor = TRUE)
* or, pass autocolor = TRUE to renderPlot()

Also another package called fresh does similar things