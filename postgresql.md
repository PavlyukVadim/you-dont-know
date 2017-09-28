## Table of Contents

  1. [Types](#types)
  1. [Create table](#create-table)
  

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

