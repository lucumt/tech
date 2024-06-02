---
title: "什么是gRPC"
weight: 1
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![什么是gRPC](/img/code/framework/grpc/what-is-grpc.gif "什么是gRPC")

What is gRPC? 

The diagram below shows important aspects of understanding gRPC. 

gRPC is a high-performance, open-source universal RPC (Remote Procedure Call) framework initially developed by Google. It leverages HTTP/2 for transport, Protocol Buffers as the interface description language, and provides features such as authentication, load balancing, and more. 
gRPC is designed to enable efficient and robust communication between services in a microservices architecture, making it a popular choice for building distributed systems and APIs. 

Key Features of gRPC: 

1. Protocol Buffers: By default, gRPC uses Protocol Buffers (proto files) as its interface definition language (IDL). This makes gRPC messages smaller and faster compared to JSON or XML. 
2. HTTP/2 Based Transport: gRPC uses HTTP/2 for transport, which allows for many improvements over HTTP/1.x. 
3. Multiple Language Support: gRPC supports a wide range of programming languages. 
4. Bi-Directional Streaming: gRPC supports streaming requests and responses, allowing for the development of sophisticated real-time applications with bidirectional communication like chat services. 