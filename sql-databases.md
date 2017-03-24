 # Relational Database
- Relational database management system (RDBMS) is a system for managing data stored in relations. Relation is essentially a mathematical term for table.
- There are a number of other ways of organizing databases. 
  - Files and directories on Unix-like operating systems form an example of a hierarchical database. 
  - A more modern development is the object-oriented database.
- Each table is a named collection of rows. Each row of a given table has the same set of named columns, and each column is of a specific data type. Whereas columns have a fixed order in each row, the order of rows within the table is not fixed in any way.
- Tables are grouped into databases, and a collection of databases managed by a single server instance constitutes a database cluster.

## Commands
- Commands are not terminated until the semicolon. SQL is case insensitive about key words and identifiers, except when identifiers are double-quoted to preserve the case.
- Comments starts with `--` or `/*`
- Querying a table: 

  ```sql
  SELECT city, (temp_hi+temp_lo)/2 AS temp_avg, date 
    FROM weather;

  SELECT * FROM weather 
    WHERE city = 'San Francisco' 
    AND prcp > 0.0;

  SELECT DISTINCT city 
    FROM weather 
    ORDER BY city;
  ```
- Joins Between Tables

  ```sql
  SELECT weather.city, weather.temp_lo, weather.temp_hi, cities.location
    FROM weather, cities 
    WHERE cities.name = weather.city;

  SELECT * 
    FROM weather w, cities c 
    WHERE w.city = c.name;
      
  -- LEFT OUTER JOIN - Return all records from left table, and matched records from right table 
  SELECT * 
    FROM weather LEFT OUTER JOIN cities ON (weather.city = cities.name);     
        
  -- RIGHT (OUTER) JOIN - Return all records from right table, and matched records from left table
  -- FULL (OUTER) JOIN - Return all records when there is a match in either left or right table 
  -- (INNER) JOIN - Returns records that have matching values in both tables
  SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
    FROM ((Orders 
    INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID) 
    INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);

  -- SELF JOIN - A self JOIN is a regular join, but the table is joined with itself
  -- The following SQL statement matches customers that are from the same city
  SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
    FROM Customers A, Customers B
    WHERE A.CustomerID <> B.CustomerID
    AND A.City = B.City
    ORDER BY A.City; 
  ```

- Aggregate Functions

  ```sql
  SELECT city 
    FROM weather WHERE temp_lo = (SELECT max(temp_lo) FROM weather);
  -- Grouping the aggregates
  SELECT city, max(temp_lo) 
    FROM weather 
    GROUP BY city;
  -- Filter the group rows using HAVING
  SELECT city, max(temp_lo)
    FROM weather
    GROUP BY city
    HAVING max(temp_lo) < 40;
  -- Pattern matching using LIKE - Cities with names starting with S
  SELECT city, max(temp_lo)
    FROM weather
    WHERE city LIKE 'S%'(1)
    GROUP BY city
    HAVING max(temp_lo) < 40;
  ```
  The fundamental difference between `WHERE` and `HAVING` is this: `WHERE` selects input rows before groups and aggregates are computed, whereas `HAVING` selects group rows after groups and aggregates are computed. 

- Updates

  ```sql
  UPDATE weather
    SET temp_hi = temp_hi - 2,  temp_lo = temp_lo - 2
    WHERE date > '1994-11-28';
  ```

- Deletions

  ```sql
  DELETE FROM weather WHERE city = 'Hayward';
  -- Danger - remove all rows from the given table
  DELETE FROM tablename;
  ```
## Features
- **Views** Views allow to encapsulate the details of the structure of your tables, which might change as the application evolves, behind consistent interfaces.

  ```sql
  CREATE VIEW myview AS
    SELECT city, temp_lo, temp_hi, prcp, date, location
      FROM weather, cities
      WHERE city = name;

  SELECT * FROM myview;
  ```
- **Foreign Keys** The Foreign keys allows maintaining *referential integrity*. In the above example while inserting a new column to *weather* table, it is checked if a matching record exists in *cities* table. The *insert* is rejected in case the record is not found.

  ```sql
  CREATE TABLE cities (
    city     varchar(80) primary key,
    location point
  );

  CREATE TABLE weather (
    city      varchar(80) references cities(city),
    temp_lo   int,
    temp_hi   int,
    prcp      real,
    date      date
  );
  ```
- **Transactions** Transaction bundles multiple steps into a single, all-or-nothing operation. Intermediate states are not visible to other concurrent transactions, and in case of a failure none of the steps affec the database at all.
## Links 
- https://www.postgresql.org/docs/9.6/static/index.html
