# LIKE

The `LIKE` operator is used in a `WHERE` clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the `LIKE` operator:

* &#x20;The percent sign (%) represents zero, one, or multiple characters
* &#x20;The underscore sign (\_) represents one, single character

```sql
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE pattern;
```
