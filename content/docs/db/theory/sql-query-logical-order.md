---
title: "SQL查询执行顺序"
weight: 7
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![扩展数据库的7种策略](/img/db/theory/sql-query-logical-order.gif)

SQL statements are executed by the database system in several steps, including:

* Parsing the SQL statement and checking its validity
* Transforming the SQL into an internal representation, such as relational algebra
* Optimizing the internal representation and creating an execution plan that utilizes index information
* Executing the plan and returning the results

---

Visualizing SQL Queries

A mental model can help visualize how SQL queries are executed. Conceptually, SQL statements execute in this sequence:

1. FROM: Tables are identified and joined to create the initial dataset.
2. WHERE: Filters are applied to the initial dataset based on specified criteria.
3. GROUP BY: The filtered rows are grouped according to the specified columns.
4. HAVING: Additional filters are applied to the grouped rows based on aggregate criteria.
5. SELECT: Specific columns are chosen from the resultant dataset for the output.
6. ORDER BY: The output rows are sorted by the specified columns in ascending or descending order.
7. LIMIT: The number of rows in the output is restricted.