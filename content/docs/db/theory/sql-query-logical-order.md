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
\- Parsing the SQL statement and checking its validity
\- Transforming the SQL into an internal representation, such as relational algebra
\- Optimizing the internal representation and creating an execution plan that utilizes index information
\- Executing the plan and returning the results