https://dplyr.tidyverse.org/reference/join.html

Join types

Currently dplyr supports four types of mutating joins, two types of filtering joins, and a nesting join.

Mutating joins combine variables from the two data.frames:

inner_join()

    return all rows from x where there are matching values in y, and all columns from x and y. If there are multiple matches between x and y, all combination of the matches are returned.
left_join()

    return all rows from x, and all columns from x and y. Rows in x with no match in y will have NA values in the new columns. If there are multiple matches between x and y, all combinations of the matches are returned.
right_join()

    return all rows from y, and all columns from x and y. Rows in y with no match in x will have NA values in the new columns. If there are multiple matches between x and y, all combinations of the matches are returned.
full_join()

    return all rows and all columns from both x and y. Where there are not matching values, returns NA for the one missing.

Filtering joins keep cases from the left-hand data.frame:

semi_join()

    return all rows from x where there are matching values in y, keeping just columns from x. A semi join differs from an inner join because an inner join will return one row of x for each matching row of y, where a semi join will never duplicate rows of x.
anti_join()

    return all rows from x where there are not matching values in y, keeping just columns from x.

Nesting joins create a list column of data.frames:

nest_join()

    return all rows and all columns from x. Adds a list column of tibbles. Each tibble contains all the rows from y that match that row of x. When there is no match, the list column is a 0-row tibble with the same column names and types as y. nest_join() is the most fundamental join since you can recreate the other joins from it. An inner_join() is a nest_join() plus an tidyr::unnest(), and left_join() is a nest_join() plus an unnest(.drop = FALSE). A semi_join() is a nest_join() plus a filter() where you check that every element of data has at least one row, and an anti_join() is a nest_join() plus a filter() where you check every element has zero rows.
