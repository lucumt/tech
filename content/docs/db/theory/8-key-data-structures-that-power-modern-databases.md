---
title: "8个关键数据结构"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![数据库中的8个关键数据结构](/img/db/theory/8-key-data-structures-that-power-modern-databases.jfif)

8 Key Data Structures That Power Modern Databases

* Skiplist: a common in-memory index type. Used in Redis
* Hash index: a very common implementation of the “Map” data structure (or “Collection”)
* SSTable: immutable on-disk “Map” implementation
* LSM tree: Skiplist + SSTable. High write throughput
* B-tree: disk-based solution. Consistent read/write performance
* Inverted index: used for document indexing. Used in Lucene
* Suffix tree: for string pattern search
* R-tree: multi-dimension search, such as finding the nearest neighbor

