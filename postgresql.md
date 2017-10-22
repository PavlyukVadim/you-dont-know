## Table of Contents

  1. [Types](#types)
  1. [Create table](#create-table)
  1. [Joins](#joins)
  1. [Window Functions](#window-functions)
  

## Types

  <a name="types--primitives"></a><a name="1.1"></a>
  - [1.1](#types--primitives) **Primitives**: built-in general-purpose data types:

    Markdown | Description
    --- | --- 
    `bigserial` | autoincrementing eight-byte integer
    `boolean` | logical Boolean (true/false)
    `character [ (n) ]` | fixed-length character string
    `date` | calendar date (year, month, day) 
    `double precision` | double precision floating-point number (8 bytes)
    `integer` | signed four-byte integer
    `text` | variable-length character string
    
**[⬆ back to top](#table-of-contents)**

## Create table
```sql
    CREATE TABLE clients (
      client_id bigserial primary key,
      second_name character(20) not null,
      first_name character(20) not null,
      phone character(15) not null,
      email character(20) not null,
      reg_date date not null default now()
    );
```
**[⬆ back to top](#table-of-contents)**

## Joins
Assume we have tables table1:

num | name
--- | --- 
`1` | a
`2` | b
`3` | c

and table2:

num | value
--- | --- 
`1` | x
`2` | y
`3` | z

then we get the following results for the various joins:
```sql
    SELECT * FROM table1 CROSS JOIN table2;
```
num | name | num | value
--- | --- | --- | --- 
`1` | a | `1` | x
`1` | a | `2` | y
`1` | a | `3` | z
`2` | b | `1` | x
`2` | b | `2` | y
`2` | b | `3` | z
`3` | c | `3` | z
`3` | c | `3` | z
`3` | c | `3` | z

**[⬆ back to top](#table-of-contents)**

## Window Functions
A window function performs a calculation across a set of table rows that are somehow related to the current row. This is comparable to the type of calculation that can be done with an aggregate function. But unlike regular aggregate functions, use of a window function does not cause rows to become grouped into a single output row — the rows retain their separate identities. Behind the scenes, the window function is able to access more than just the current row of the query result.

Here is an example that shows how to compare each employee's salary with the average salary in his or her department:

```sql
  SELECT depname, empno, salary, avg(salary) OVER (PARTITION BY depname) FROM empsalary;
```

  depname  | empno | salary |          avg          
-----------|-------|--------|----------------------
 develop   |    11 |   5200 | 5020.0000000000000000
 develop   |     7 |   4200 | 5020.0000000000000000
 develop   |     9 |   4500 | 5020.0000000000000000
 develop   |     8 |   6000 | 5020.0000000000000000
 develop   |    10 |   5200 | 5020.0000000000000000
 personnel |     5 |   3500 | 3700.0000000000000000
 personnel |     2 |   3900 | 3700.0000000000000000
 sales     |     3 |   4800 | 4866.6666666666666667
 sales     |     1 |   5000 | 4866.6666666666666667
 sales     |     4 |   4800 | 4866.6666666666666667

A window function call always contains an OVER clause directly following the window function's name and argument(s). This is what syntactically distinguishes it from a regular function or aggregate function. The OVER clause determines exactly how the rows of the query are split up for processing by the window function. The PARTITION BY list within OVER specifies dividing the rows into groups, or partitions, that share the same values of the PARTITION BY expression(s). For each row, the window function is computed across the rows that fall into the same partition as the current row.

You can also control the order in which rows are processed by window functions using ORDER BY within OVER. (The window ORDER BY does not even have to match the order in which the rows are output.) Here is an example:

```sql
  SELECT depname, empno, salary, rank() OVER (PARTITION BY depname ORDER BY salary DESC) FROM empsalary;
```

  depname  | empno | salary | rank 
-----------|-------|--------|------
 develop   |     8 |   6000 |    1
 develop   |    10 |   5200 |    2
 develop   |    11 |   5200 |    2
 develop   |     9 |   4500 |    4
 develop   |     7 |   4200 |    5
 personnel |     2 |   3900 |    1
 personnel |     5 |   3500 |    2
 sales     |     1 |   5000 |    1
 sales     |     4 |   4800 |    2
 sales     |     3 |   4800 |    2

**[⬆ back to top](#table-of-contents)**
