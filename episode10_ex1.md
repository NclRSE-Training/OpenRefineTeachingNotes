## Reformat the Date

1. Make sure you remove all Facets and Filters
1. On the Date column use the dropdown menu to select Edit cells -> Transform
1. In the ‘Expression’ box type the GREL expression value.toDate("dd/MM/yyyy") and press OK.
1. Note how the values are now displayed in green and follow a standard convention for their display format (ISO 8601) - this indicates they are now stored as date data types in OpenRefine. We can now carry out functions that are specific to Dates
1. On the Date column dropdown select Edit column->Add column based on this column. Using this function you can create a new column, while preserving the old column
1. In the ‘New column name’ type “Formatted-Date”
1. In the ‘Expression’ box type the GREL expression value.toString("dd MMMM yyyy")

[Episode 10 exercise 2](episode10_ex2.md)
