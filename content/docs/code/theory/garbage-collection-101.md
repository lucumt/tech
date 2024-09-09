---
title: "垃圾回收工作流程"
weight: 12
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![garbage-collection-101](/img/code/theory/garbage-collection-101.gif)

How does Garbage Collection work? 
Garbage collection is an automatic memory management feature used in programming languages to reclaim memory no longer used by the program. 

🔹 Java 
Java provides several garbage collectors, each suited for different use cases: 

\1. Serial Garbage Collector: Best for single-threaded environments or small applications. 

\2. Parallel Garbage Collector: Also known as the "Throughput Collector." 

\3. CMS (Concurrent Mark-Sweep) Garbage Collector: Low-latency collector aiming to minimize pause times. 

\4. G1 (Garbage-First) Garbage Collector: Aims to balance throughput and latency. 

\5. Z Garbage Collector (ZGC): A low-latency garbage collector designed for applications that require large heap sizes and minimal pause times. 

🔹 Python 
Python's garbage collection is based on reference counting and a cyclic garbage collector: 

\1. Reference Counting: Each object has a reference count; when it reaches zero, the memory is freed. 

\2. Cyclic Garbage Collector: Handles circular references that can't be resolved by reference counting. 

🔹 GoLang 
Concurrent Mark-and-Sweep Garbage Collector: Go's garbage collector operates concurrently with the application, minimizing stop-the-world pauses. 