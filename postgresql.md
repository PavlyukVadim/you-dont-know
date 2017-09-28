## Table of Contents

  1. [Types](#types)
  1. [Create table](#create-table)
  1. [Joins](#joins)
  

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
