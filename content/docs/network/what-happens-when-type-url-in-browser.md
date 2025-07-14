---
title: "浏览器如何处理网络请求"
weight: 11
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![浏览器如何处理网络请求](/img/network/what-happens-when-type-a-url-into-a-browser.gif)

What happens when you type a URL into a browser?

Let’s look at the process step by step.

* Step 1: The user enters a URL (bytebytego .com) into the browser and hits Enter. The first thing we need to do is to translate the URL to an IP address. The mapping is usually stored in a cache, so the browser looks for the IP address in multiple layers of cache: the browser cache, OS cache, local cache, and ISP cache. If the browser couldn’t find the mapping in the cache, it will ask the DNS (Domain Name System) resolver to resolve it.
* Step 2: If the IP address cannot be found at any of the caches, the browser goes to DNS servers to do a recursive DNS lookup until the IP address is found.
* Step 3: Now that we have the IP address of the server, the browser sends an HTTP request to the server. For secure access of server resources, we should always use HTTPS. It first establishes a TCP connection with the server via TCP 3-way handshake. Then it sends the public key to the client. The client uses the public key to encrypt the session key and sends to the server. The server uses the private key to decrypt the session key. The client and server can now exchange encrypted data using the session key.
* Step 4: The server processes the request and sends back the response. For a successful response, the status code is 200. There are 3 parts in the response: HTML, CSS and Javascript. The browser parses HTML and generates DOM tree. It also parses CSS and generates CSSOM tree. It then combines DOM tree and CSSOM tree to render tree. The browser renders the content and display to the user.