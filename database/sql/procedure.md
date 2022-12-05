# PROCEDURE

### Stored Procedure

```sql
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;
```

### Execute

```sql
EXEC procedure_name;
```

### Stored Procedure With One Parameter

```sql
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30)
AS
SELECT * FROM Customers WHERE City = @City
GO;
```

### Execute

```sql
EXEC SelectAllCustomers @City = 'London';
```

### Stored Procedure With Multiple Parameters

```sql
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;
```

### Execute

```sql
EXEC SelectAllCustomers @City = 'London', @PostalCode = 'WA1 1DP';
```
