---
layout: blog
title: Insights and Reflections on Knowledge Graph Construction at DoorDash
---
# Knowledge Graph: A Brief Overview and Creation Guide

A **knowledge graph** is a structured representation of entities and their relationships within a system or domain. 

In this post, I want to briefly talk about how to create a knowledge graph. At DoorDash, understanding products and their attributes is crucial for customer recommendations and brand advertisements. For example, when a new product like Coke is added, we need to determine its relationships, such as:

(coca-cola company) -[manufactures]-> (coke)

## How to Extract Entities?

This process is called **Named-Entity Recognition (NER)**.

1. **Brute Force (Manual Annotation)**
   - Manually labeling entities in the dataset.
   - **Cons**:
     - Not scalable.
     - Costly and inefficient.
     - **Not recommended** for DoorDash, which processes large amounts of input data daily.

2. **String Matching + Classifier**
   - Uses string matching combined with a classifier to verify if an entity passes a defined threshold.
   - **Pros**:
     - High precision.
     - Decent coverage.
   - **Cons**:
     - Only work for obvious patterns.

There are some more classic ways to perform entity extraction, but what if we leverage **LLMs** to assist us? LLMs have contextual and semantic understanding that can improve the process.

3. **Using LLMs to Identify Attributes**
   - Suitable for simple and common attributes such as identifying a product's brand.

What if we need additional attributes with deeper meanings that are not explicitly stated on product labels or descriptions, or specialized attributes unique to this product?

4. **Few-Shot Prompting via Embedding Similarity**
   - Retrieve similar but labeled products using **embedding similarity**.
   - Use **few-shot prompting** to guide the LLM based on known examples.

5. **LLM Reasoning**
   - Make the LLM "think" and deduce results.
   - **Example**: An LLM could analyze a product's packaging photo and infer whether it is organic.

6. **LLM Agent**
   - A specialized software system with an **LLM core** and **Pre-defined goals** and characteristics.
   - We can use it to autonomously perform specific tasks.


### Reference

[Building DoorDash's Product Knowledge Graph with Large Language Models](https://careersatdoordash.com/blog/building-doordashs-product-knowledge-graph-with-large-language-models)
