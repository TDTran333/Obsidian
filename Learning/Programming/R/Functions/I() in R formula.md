---
tags: R
---
Link: [StackOverflow](https://stackoverflow.com/questions/8055508/in-r-formulas-why-do-i-have-to-use-the-i-function-on-power-terms-like-y-i)

# I() in R formula
The I() function acts to convert the argument to "as.is", i.e. what you expect. So I(x^2) would return a vector of values raised to the second power.

The issue here is how formulas are interpreted. The infix operators "+", "*", ":" and "^" have entirely different meanings than when used with numeric vectors. In a formula the tilde separates the left hand side from the right hand side. In formulas the ^ operator is for constructing interactions so that x = x^2 = x^3 rather than the perhaps expected mathematical power. (A variable interacting with itself is just the same variable.) If you had typed (x+y)^2 the R interpreter would have produced (for its own good internal use), not a mathematical: x^2 +2xy +y^2 , but rather a symbolic: x + y +x:y where x:y is an interaction term.

