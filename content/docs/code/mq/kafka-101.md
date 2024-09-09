---
title: "Kafka核心概念"
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![Kafka核心概念](/img/code/mq/kafka-101.gif "Kafka核心概念")

The Ultimate Kafka 101 You Cannot Miss 

Kafka is super-popular but can be overwhelming in the beginning. 

Here are 8 simple steps that can help you understand the fundamentals of Kafka. 

1 - What is Kafka? 
Kafka is a distributed event store and a streaming platform. It began as an internal project at LinkedIn and now powers some of the largest data pipelines in the world in orgs like Netflix, Uber, etc. 

2 - Kafka Messages 
Message is the basic unit of data in Kafka. It’s like a record in a table consisting of headers, key, and value. 

3 - Kafka Topics and Partitions 
Every message goes to a particular Topic. Think of the topic as a folder on your computer. Topics also have multiple partitions. 

4 - Advantages of Kafka 
Kafka can handle multiple producers and consumers, while providing disk-based data retention and high scalability. 

5 - Kafka Producer 
Producers in Kafka create new messages, batch them, and send them to a Kafka topic. They also take care of balancing messages across different partitions. 

6 - Kafka Consumer 
Kafka consumers work together as a consumer group to read messages from the broker. 

7 - Kafka Cluster 
A Kafka cluster consists of several brokers where each partition is replicated across multiple brokers to ensure high availability and redundancy. 

8 - Use Cases of Kafka 
Kafka can be used for log analysis, data streaming, change data capture, and system monitoring. 

Over to you: What else would you add to get a better understanding of Kafka? 