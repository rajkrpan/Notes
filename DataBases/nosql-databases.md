# NoSQL DataBase

## Cassandra
- Cassandra is a NoSQL database for managing large amounts of structured, semi-structured, and unstructured data across multiple data centers, and delivers continuous availability and linear scalability.
- The CAP theorem, states that it is impossible for a distributed computer system to simultaneously provide all three of the following guarantees:
  - Consistency (all nodes see the same data at the same time)
  - Availability (a guarantee that every request receives a response about whether it was successful or failed)
  - Partition tolerance (the system continues to operate despite arbitrary message loss or failure of part of the system)
- Cassandra is typically classified as an AP system.
- Internal Data Structure: A Cassandra data model consist of
  - Keyspaces           | Database
  - Column Families     | Table
  - Row Key             | Primary Key
  - Column Name/Key     | Column Name
  - Column Value        | Column Value 

  ```                   
  Map<RowKey, SortedMap<ColumnKey, ColumnValue>>
  ```
  - Rows and Columns both are sorted by rowkeys and columnkeys respectively.
- CQL commands are similar to SQL, e.g.

  ```sql
  SELECT * FROM MyTable;

  UPDATE MyTable
    SET SomeColumn = 'Some Value'
    WHERE columnName = 'Something Else';
  ```
  Keyspace, column name and table name created using CQL are case insensitive unless enclosed in double quotation mark.


## Links
- https://teddyma.gitbooks.io/learncassandra/content/
- http://docs.datastax.com/en/cql/3.1/cql/cql_reference/cqlCommandsTOC.html (List of all CQL commands)
