https://uvastatlab.github.io/phdplus/installR.html

#### To update R on Windows, try using the package installr (only for Windows)

Install and load installr: install.packages("installr") and library(installr)
Call updateR() function. This will start the updating process of your R installation by: “finding the latest R version, downloading it, running the installer, deleting the installation file, copy and updating old packages to the new R installation.”

#### Update your R packages:

update.packages(ask = FALSE, checkBuilt = TRUE)