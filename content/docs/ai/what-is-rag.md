---
title: "RAG概念解释"
weight: 4
# bookFlatSection: false
# bookToc: true
# bookHidden: false
# bookCollapseSection: false
# bookComments: false
# bookSearchExclude: falce
---

![RAG概念解释](/img/ai/what-is-rag.gif)

What is Retrieval-Augmented Generation (RAG)?

RAG augments LLM outputs by referencing authoritative knowledge bases outside the model's training data before generating responses.

This approach extends LLM capabilities to specialized domains without requiring expensive retraining or fine-tuning.

How RAG Works:

1. **Prompt + Query**
   The user submits a prompt through the LLM interface. The server converts this query into a vector representation.

2. **Query**
   The vectorized query is sent to the search system.

3. **Fetch Information**
   The search system retrieves relevant information from various knowledge sources—PDFs, databases, documents, code repositories, web search, and APIs.

4. **Relevant Information for Enhanced Context**
   The fetched information is sent back to the RAG model to augment the original query.

5. **Prompt + Query + Enhanced Context**
   The system combines the original user input with the retrieved information, creating an enriched prompt that's sent to the LLM endpoint (GPT, Claude, Gemini, etc.).

6. **Generated Text Response**
   The LLM generates a contextually-aware answer based on the enhanced context and returns it to the user.

This architecture solves the knowledge cutoff problem while maintaining the LLM's conversational abilities and reasoning power.