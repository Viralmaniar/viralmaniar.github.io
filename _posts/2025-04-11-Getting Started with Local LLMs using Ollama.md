---
layout: single
classes: wide
author_profile: true
read_time: true
share: true
related: true
title:  "Getting Started with Local LLMs using Ollama"
date:   2025-04-11 00:19:05 +1000
categories:
  - Artificial Intelligence (AI)
  - Machine Learning (ML)
tags:
  - AI Security
  - LLM
  - Ollama
---

Large Language Models (LLMs) have revolutionised the way we interact with machines. While powerful cloud-hosted LLMs come with trade-offs in terms of cost, limited API calls, credits and privacy. This is where Ollama comes in handy. It is a tool designed to run open-source LLMs locally with ease.

In this blog, we will break down what LLMs are, how tools like Ollama can help run LLMs locally on a machine and how to build a local Retrieval Augmented Generation (RAG) setup with a vector database and your own custom model.

# What is a Large Language Model (LLM)?

An LLM is a type of deep learning model trained on massive text datasets to understand and generate human-like text. Examples include:
 - GPT 4 by OpenAI
 - LLaMA by Meta
 - Mistral
 - Phi by Microsoft etc

These models perform tasks like summarization, Q&A, and code generation. They’re general-purpose but can be fine-tuned or extended to specific domains.

# What is a Vector Database?
A vector database stores text embeddings (numerical representations of meaning) to make semantic search fast and accurate.
Popular options:
- ChromaDB (best for local use)
- FAISS (Facebook AI Similarity Search): Allows developers to quickly search for embeddings of multimedia documents that are similar to each other.
- Weaviate 
- Pinecone

These databases allow the system to find documents based on meaning not just keywords.

# What is RAG (Retrieval Augmented Generation)?

LLMs are powerful but can hallucinate facts. To solve this problem we have RAG - a technique that combines:
 - Retrieval: Fetch real documents from an external source (like a vector DB)
 - Generation: Use the LLM to generate a response based on the retrieved information

Now that you know some basics of a few terms that are common in the AI world. Let's go ahead and install Ollama on the machine

# Setting Up: Installing Ollama

Go to https://ollama.com/download and download for your OS (Mac, Windows, or Linux).
![image](https://github.com/user-attachments/assets/316ab9be-8fed-46b2-ab33-822947b5e3de)

I am running WSL on a Windows 11 machine and downloading it via a simple Curl command:

`curl -fsSL https://ollama.com/install.sh | sh`

![image](https://github.com/user-attachments/assets/67e85a92-0b0a-4ca8-86b7-c43cb10a5cad)

After successful installation. Let's verify and look for flags related to Ollama using below:

` ollama --help `

![image](https://github.com/user-attachments/assets/238311f1-192b-4659-bfcb-c81870844847)



