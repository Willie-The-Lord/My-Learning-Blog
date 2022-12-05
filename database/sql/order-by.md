# ORDER BY

### ORDER BY Several Columns Example

The following SQL statement selects all customers from the "Customers" table, sorted by the "Country" and the "CustomerName" column. This means that it orders by Country, but if some rows have the same Country, it orders them by CustomerName:

```sql
SELECT * FROM Customers
ORDER BY Country, CustomerName;
```

### ORDER BY Several Columns Example 2

The following SQL statement selects all customers from the "Customers" table, sorted ascending by the "Country" and descending by the "CustomerName" column:

```sql
SELECT * FROM Customers
ORDER BY Country ASC, CustomerName DESC;
```

### Resource

[https://www.w3schools.com/sql/sql\_orderby.asp](https://www.w3schools.com/sql/sql\_orderby.asp)
