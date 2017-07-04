# SQL Guideline

## `GROUP BY` vs `DISTINCT`

### Using something else than MySQL

MySQL is quite easy to use regarding `GROUP BY` statements. However, as soon you're moving to another engine/server, they might create errors like:

`Column is invalid in the select list because it is not contained in either an aggregate function or the GROUP BY clause`

A nice quote from [Stackoverflow](https://stackoverflow.com/questions/1122436/sql-server-group-by-error):

```
Yes, MySQL would let you do that, and it would return what you ask for. 
The problem with that is that what you ask for is unspecific, so the result is equally unspecific. 
It will return one of the column values from each group, but it won't care which one.
```

Using `DISTINCT` (and editing the query ofc) or replacing the `GROUP BY` through an `ORDER BY` may help here, depending on the needed result. 


Again, from [Stackoverflow](https://stackoverflow.com/questions/8992804/how-sqls-distinct-clause-works):

`DISTINCT` filters out duplicate values of your returned fields.

A really simplified way to look at it is:

- It builds your overall result set (including duplicates) based on your `FROM` and `WHERE` clauses
- It sorts that result set based on the fields you want to return
- It removes any duplicate values in those fields

It's semantically equivalent to a `GROUP BY`  where all returned fields are in the `GROUP BY` clause.


### Using MySQL

If the following error occurs in MySQL, then `ONLY_FULL_GROUP_BY` is activated in the current SQL mode. WAMP allows to quickly change the SQL mode by clicking on the tray icon > MySQL > MySQL settings > sql-mode.

`Expression of SELECT list is not in GROUP BY clause and contains nonaggregated column which is not functionally dependent on columns in GROUP BY clause.`
