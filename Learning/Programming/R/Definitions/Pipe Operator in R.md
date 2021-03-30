---
tags: R
---
Link: [Website](https://www.datacamp.com/community/tutorials/pipe-r-tutorial)
Related: [R adds native pipe `|>`](https://developer.r-project.org/blosxom.cgi/R-devel/NEWS/2020/12/04#n2020-12-04)

# Pipe Operator in R
### Brief history
* Mathematical History : Chaining function
	* f(g(x)): g(x) serves as an input for f(), while x serves as input to g().
* Programming History: The operator is not new. Shell has `|`.
* Pipes in R
	* magrittr and dplyr, 2013/2014

### What is the pipe operator?
In R, the pipe operator `%>%` takes the output of one statement and makes it the input of the next statement. When describing it, you can think of it as a "THEN".

### Why use the pipe operator?
R is primarily a functional programming language and that means that codes contains alot of parenthesis. The pipe operator makes the code easier to read and more flexible.

Using pipes in R:
-   Structures the sequence of operations from left to right instead of from inside and out.
-   Avoids nested function calls.
-   Minimizes the need for local variables and function definitions.
-   Makes it easy to add steps anywhere in the sequence of operations.

### Other type of pipes
There's a few more pipe operators in the `magrittr` package.

* The assignment pipe operator `%<>%`
	* Pipe an object forward into a function or call expression and update the `lhs` object with the resulting value.
* The tee pipe operator `%T>%`
	* Pipe a value forward into a function- or call expression and return the original value instead of the result. This is useful when an expression is used for its side-effect, say plotting or printing.
* The exposition pipe operator `%$%`
	* Expose the names in `lhs` to the `rhs` expression. This is useful when functions do not have a built-in data argument.

### Basic of pipes in R
*   `f(x)` can be rewritten as `x %>% f`
	*   `argument %>% function()`
*   `f(x, y)` can be rewritten as `x %>% f(y)`
	*   `argument1 %>% function(argument2)`
* `x %>% f %>% g %>% h` can be rewritten as `h(g(f(x)))`
* `f(x, y)` can be rewritten as `y %>% f(x, .)`
* `f(y, z = x)` can be rewritten as `x %>% f(y, z = .)`

### When Not To Use the Pipe Operator in R
* Pipes sequences are longer than (say) ten steps.
* Multiple inputs or outputs.
* Directed graph with a complex dependency structure.
* Internal package development.

### Alternatives to Pipes in R
* Create intermediate variables with meaningful names.
* Use tabs to highlight the hierarchy in nested codes.

### The end goal is readability