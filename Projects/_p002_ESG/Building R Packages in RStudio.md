Building R Packages in RStudio
 	
![[Pasted image 20201113172426.png]]







devtools::use_package()
devtools::load_all()
usethis::use_testthat() devtools::test()
devtools::document()
usethis::use_vignette()
usethis::use_data()
@export @import

Tutorial / Screencast by David Robinson: https://www.youtube.com/watch?v=F4oUJp76KUY
The process of creating R package includes:
•	Filling out the DESCRIPTION file
•	Creating datasets with a script in data-raw and saving them to data
•	Documenting the datasets with Roxygen2 and devtools::document()
•	Publishing to GitHub
 
 ![[Pasted image 20201113172436.png]]
 
Roxygen2 package to generate R documentation
https://cran.r-project.org/web/packages/roxygen2/vignettes/roxygen2.html
•	Add roxygen comments to source file. 
•	roxygen2::roxygenise() converts roxygen comments to .Rd files. 
•	R converts.Rd files to human readable documentation. 
Object documentation: https://r-pkgs.org/man.html
Vignettes: long-form documentation: https://r-pkgs.org/vignettes.html
See https://r-pkgs.org/ for complete documentation
 
 ![[Pasted image 20201113172445.png]]
 
Documenting datasets

![[Pasted image 20201113172455.png]]

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
•	The first sentence becomes the title of the documentation.
•	The second paragraph is the description
•	The third and subsequent paragraphs go into the details
•	@seealso allows you to point to other useful resources 

 ![[Pasted image 20201113172507.png]]

Useful links
•	Devtools-cheatsheet
https://www.rstudio.com/wp-content/uploads/2015/06/devtools-cheatsheet.pdf
•	Package Development in R
https://iqss.github.io/dss-rbuild/
•	R Packages by Hardley Wickham
https://r-pkgs.org/
•	Creating R Packages on CRAN
https://cran.r-project.org/doc/manuals/R-exts.html