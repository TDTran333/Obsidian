---
tags: R
---
# Defensive R Programming
## R Packages
### Consideration for choosing an R package
Is the package
* mature?
* actively developed?
* well documented? Are there any available vignette?
* well used?

Where are you using the package?
* Toy project?
* Production server?

### CRAN Task Views
CRAN task views aim to provide some guidance which packages on CRAN are relevant for tasks related to a certain topic. They are curated by experts in a particular field. They give a brief overview of the included packages and can be automatically installed using the [ctv](https://CRAN.R-project.org/package=ctv) package. The views are intended to have a sharp focus so that it is sufficiently clear which packages should be included (or excluded) - and they are _not_ meant to endorse the "best" packages for a given task.

See: [[Cran Task Views]]

##### old.packages()
old.packages indicates packages which have a (suitable) later version on the repositories

##### update.packages()
update.packages offers to download and install such packages.

### Your Global Environment
* The default environment is the .GlobalEnv
* Objects are stored in environments
* To view the contents, use ls()
* This environment quickly fills up
* We can start to mixing up objects

### Packages and Environments
* Packages use namespaces as spaces for names
	* The namespace is like a box that contains the package functions
* A namespace helps keep things tidy
	* Sort of like folders 

##### library() 
Gives direct access to this package box. Loading/Attaching and Listing of Packages

##### getNamespaceExports()
Returns a character vector of the names exported by the package.

##### `::` operator
For a package pkg, pkg::name returns the value of the exported variable name in namespace pkg, whereas pkg:::name returns the value of the internal variable name. The package namespace will be loaded if it was not loaded before the call, but the package will not be attached to the search path.

### Same Function Names
Sometimes package authors come with the same function name. If you use a function without referring to the package, R will select the function according to the package load order. Namespace clashes can lead to hard to diagnose bugs.

##### search()
Gives a list of attached packages in the package load order.

#### library(conflicted)
Automatically highlight potential package clashes and forces the user to make a clear choice.

##### conflicted()
 'conflicted' takes a different approach, making every conflict an error and forcing you to choose which function to use.
 
 ##### conflict_prefer()
 Persistently prefer one function over another.
 
 ## Early warning systems
 R techniques for notifying the user
 * Avoid problems where possible 
 * Handle issues are they arise in a sensible way
 
 ### Example: TRUE and FALSE
* Special values
* Can't be overriden
* T and F are shortcuts for TRUE and FALSE but they aren't protected

##### isTRUE() and isFALSE()
Test logical value.

### Messages
Messages are useful for providing feedback on a functions progress.
See: [[R Output Overview]]

##### message()
Generate a diagnostic message from its arguments. Can be used to signal to the user the state of a process. It is not an error, it is just helpful information.

##### suppressMessages()
suppressMessages evaluates its expression in a context that ignores all ‘simple’ diagnostic message.

### Telling packages to be quiet
 ##### suppressPackageStartupMessages()
Aptly named.

### Warning
Warnings indicate something may have gone wrong in the code, but you can still proceed.
* Signals that something may have gone wrong
* R continues (unlike an error)
* "Warning message:" is pre-appended

##### warning()
Generates a warning message that corresponds to its argument(s) and (optionally) the expression or function from which it was called.

##### suppressWarnings()
suppressWarnings evaluates its expression in a context that ignores all warnings.

### Stop
You can't suppress or ignore errors. R can't continue.

##### stop()
stop stops execution of the current expression and executes an error action.

##### try()
try is a wrapper to run an expression that might fail and allow the user's code to handle error-recovery. It tries to execute something, it if doesn't work, it moves on. The object result contains details about the error.

## Avoiding Mistakes
### Be DRY: Do not Repeat Yourself
* Avoid coping and pasting
* Reuse, when appropriate, existing tools

### Avoid WET: Writing Everthing Twice

### Copy and Paste rule
* Copying and pasting once is OK
* Twice is suspect
* Three times is almost always wrong

Whenever you copy & paste, consider
* A function
* Or a for loop

### Commenting
Code that is obvious today ...
Is often a lot less obvious in a few weeks times

Writing good comments is hard.
* Avoid obvious comments
* Avoid comments that you will never update
* Be consistent
	* Always start with a single \#
	* Start with a capital letter - folow the rules of grammar
	* Be sure to comment on code that "looks wrong"
	* Use # TODO to indicate possible future improvements

### Avoid using . in variable names or function names
It leads to confusion with S3 objects.

### Coding Style
The crucial aspect of a coding style is consistency
In practice, you may have to adjust your style to fit in with your collaborators

### Spacing
Consistent spacing makes code far easier to read
* Use spaces around assignment operators
* Add a space after a comma

### Static Code Analysis for R
#### library(lintr)
It checks adherence to a given style, syntax errors and possible semantic issues

## Structure of R Projects
### Break the work into small and manageable chunk
### Sensible filenames are important
* Don't use spaces in filenames
* Dashes or underscores
	* Google treats file_name as a single word
		* So searching for just file won't work
	* The regular expression character \w treats _ as a character

### Human Readable Filenames
When possible, provide information in the filename

### Dates : Use ISO8601
Unambiguous
Sortable in a file system

### Organizing Projects
* One base directory per project
* One input / data directory for data
* One R / code directory for R code
* Use simple descriptive names (i.e clean.R, functions.R, analysis.R, graphics.R)

### Graphics and output
* output directory for generated data files
* graphics directory for generated plots