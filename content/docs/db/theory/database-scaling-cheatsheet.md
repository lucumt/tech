---
title: "扩展数据库的7种策略"
weight: 6
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![扩展数据库的7种策略](/img/db/theory/database-scaling-cheatsheet.gif)

7 must-know strategies to scale your database. 

1 - Indexing: 
Check the query patterns of your application and create the right indexes. 

2 - Materialized Views: 
Pre-compute complex query results and store them for faster access. 

3 - Denormalization: 
Reduce complex joins to improve query performance. 

4 - Vertical Scaling 
Boost your database server by adding more CPU, RAM, or storage. 

5 - Caching 
Store frequently accessed data in a faster storage layer to reduce database load. 

6 - Replication 
Create replicas of your primary database on different servers for scaling the reads. 

7 - Sharding 
Split your database tables into smaller pieces and spread them across servers. Used for scaling the writes as well as the reads. 

Over to you: What other strategies do you use for scaling your databases? 