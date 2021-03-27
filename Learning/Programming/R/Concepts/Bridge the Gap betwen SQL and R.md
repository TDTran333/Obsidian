---
tags: R
---
Link: [YouTube](https://www.youtube.com/watch?v=JwP5KdWSgqE)

# Bridge the Gap betwen SQL and R
50th anniversary of SQL
Vastly more people use SQL than R
Most of them learn SQL first

### dplyr and SQL are similar

| SQL      | Corresponding dplyr        |
| :------- | :------------------------- |
| SELECT   | select() for columns       |
|          | mutate() for expressions   |
|          | summarize() for aggregates |
| FROM     | selected data frame        |
| WHERE    | filter()                   |
| GROUP BY | group_by()                 |
| HAVING   | filter() after group_by()  |
| ORDER BY | arrange()                  |
| LIMIT    | head()    or slice()       |

### dbplyr
Translate dplyr to SQL

##### show_query()
Show the equivalent SQL query

### What about translating SQL to dplyr?
#### sqldf package
Copy data into internal database, use SQL syntax and output R dataframe
It can be impractical with bigger data

### A alternative solution would require two steps:
1. Parse SQL query
2. Apply manipulation

#### queryparse package
* Has no dependencies; implemented as pure R code
* Includes an option to use tidyverse functions in translated R expressions
* Performs semantic (not literal) translations
* Is secure by default

#### How queryparser works
1. Split query into clauses
2. Split clauses into strings containing SQL expressions
3. Manipulate strings to change them from SQL expressions to R-ish expressions
4. Parse the R-ish expressions with str2lang()
5. Apply a combination of quoting, substitution, unquoting, deparsing, string manipulation, and reparsing
6. Manipulate the abstract syntax tree
7. Check for validity
8. Return list

#### tidyquery package
Query R data frames with SQL SELECT statements
* Use it like sqldf
* Can also use it like a dplyr verb

#### How tidyquery works
1. Call queryparser::parse_query()
2. Determine which sequence of dplyr verbs to call
3. Use dplyr with rlang to evaluate the expressions in the context of the data frame]

##### show_dplyr()
Show the equivalent dplyr code.

#### Current limitations
queryparser and tidyquery do not support:
* Subqueries
* Unions
* SQL-89-style (implicit) join notations
* Joins of three or more tables
* WITH clause (common table expressions)
* OVER expressions (window or analytic functions)
* NON-ASCII characters in queries