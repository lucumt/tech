---
title: "SSH是如何工作的"
weight: 9
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: false
---

![SSH是如何工作的](/img/network/how-ssh-works.jfif)

SSH Under the Hood

* Secure Shell (SSH) creates an encrypted channel between client and server.
* The process begins with a TCP connection, followed by version negotiation.
* Both parties then agree on encryption algorithms, key exchange methods, and message authentication codes.
* The client and server perform a key exchange (typically using Diffie-Hellman) to securely generate a shared session key for encrypting the connection.
* For authentication, SSH commonly uses public key authentication.
* The server verifies the client's identity through a challenge-response mechanism using the client's public key, without the private key ever being transmitted.
* Once authenticated, the session key encrypts all further communication, providing a secure channel.

