#SQL
[SQLite tutorial point](https://www.tutorialspoint.com/sqlite/sqlite_create_table.htm)
###create table
```
sqlite> create table employee(
   ...> eID int primary key not null,
   ...> name text not null,
   ...> age int not null,
   ...> salary real not null,
   ...> dID int not null);
```
###insert value
```
insert into employee values(0, "Jim", 25, 67000.0, 0);
```
###left outter join
```
select name, ifnull(dName, "error") from employee left outer join department on employee.dID = department.dID;
```
##having
Having must be used after group by, to filter groups that are displayed in the end. 
##order by
If there are **group by** or **having** in the query, order by must be placed behind them.

##join

###cross join
A CROSS JOIN matches every row of the first table with every row of the second table. If the input tables have x and y columns, respectively, the resulting table will have x*y columns. Because CROSS JOINs have the potential to generate extremely large tables, care must be taken to only use them when appropriate.

###inner join
A INNER JOIN creates a new result table by combining column values of two tables (table1 and table2) based upon the join-predicate. The query compares each row of table1 with each row of table2 to find all pairs of rows which satisfy the join-predicate. When the join-predicate is satisfied, column values for each matched pair of rows of A and B are combined into a result row.

An INNER JOIN is the most common type of join and is the default type of join. You can use INNER keyword optionally.

###Natural Join
A NATURAL JOIN is similar to a JOIN...USING, only it automatically tests for equality between the values of every column that exists in both tables

###Outter Join (SQlite only support left outter join)
The OUTER JOINs have a condition that is identical to INNER JOINs, expressed using an ON, USING, or NATURAL keyword. The initial results table is calculated the same way. Once the primary JOIN is calculated, an OUTER join will take any unjoined rows from one or both tables, pad them out with NULLs, and append them to the resulting table.

##useful but forgettful stuff
###Round
Round(number, digits)

###date
compare date by date>="2013-03-31"