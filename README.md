# Project Outupt files

This repository contains the non-minified versions of the outputs of each component over the following query:

```sql
DELIMITER //
  select 1 + 2 * 3//
DELIMITER ;
  with
    books as (select * from books where id = 2),
    peeps as (select * from people where name = "John")
  select 
    b.1stEdition,
    avg(length) over (partition by b.name) as 'Avg Runtime'
  from books b, peeps p;
DELIMITER #
  select CURRDATE
    union
  select 2
    intersect
  select 3#
```

## File Meaning

* lexer_output.txt - txt output from the lexer
* parser_output.txt - txt output from the parser
* analyzer_output.json - JSON output from the analyzer
