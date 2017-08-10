###Filter in Calculate : Multiple Filter Optimization
- [Link to sqlbi - Marco Russo] https://www.sqlbi.com/articles/filter-vs-calculatetable-optimization-using-cardinality-estimation/
- In the following multiple filter
```sql
OrdersInPlaceSingleFilter :=
CALCULATE (
    COUNTROWS ( 'Internet Sales' ),
    FILTER (
        ALL ( 'Internet Sales' ),
        'Internet Sales'[Ship Date] >= MAX ( 'Date'[Date] )
        && 'Internet Sales'[Order Date] <= MAX ( 'Date'[Date] )
    )
)
 
OrdersInPlaceDoubleFilter :=
CALCULATE (
    COUNTROWS ( 'Internet Sales' ),
    FILTER (
        ALL ( 'Internet Sales'[Ship Date] ),
        'Internet Sales'[Ship Date] >= MAX ( 'Date'[Date] )
    ),
    FILTER (
        ALL ( 'Internet Sales'[Order Date] ),
        'Internet Sales'[Order Date] <= MAX ( 'Date'[Date] )
    )
)
```
- The measure `OrdersInPlaceSingleFilter` iterates all the 60398 rows in Internet Sales. The measure `OrdersInPlaceDoubleFilter` executes two filters iterating the 1124 unique values of the columns Ship Date and Order Date of Internet Sales table, for 2248 iterations. 
- The `OrdersInPlaceDoubleFilter` will be an order of magnitude faster in iterating the filter conditions of the `CALCULATE` statement.
- There is one exception to the above rule. In certain conditions, the filter arguments applied to CALCULATE might produce a temporary Cartesian product of all the combinations of the elements you are considering. If this would happen, the internal evaluation of 1,263,376 combinations would be slower than iterating all the 60,398 rows of Internet Sales.

## How to use KEEPFILTERS
- KEEPFILTERS modify the semantics of CALCULATE so that the new filter will not replace any existing filter but will be merged in AND with any previous filters.
- https://www.sqlbi.com/articles/keepfilters-a-new-dax-feature-to-correctly-compute-over-arbitrary-shaped-sets/

## Variables in DAX
- The VAR keyword introduces the definition of a variable. You can have as many variables as needed in a single expression, and each one has its own VAR definition. The RETURN keyword defines the expression to return as the result. Inside RETURN expression, you can use the variables, which are replaced by the computed value.
- Variables lead to the single evaluation of complex subexpression. The DAX optimizer use variables to guarantee that their evaluation happens only once, resulting in much faster code, whenever you had the same subexpression that needs to be evaluated more than once.
