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

## Step 1: Install Ollama

Go to https://ollama.com/download and download for your OS (Mac, Windows, or Linux).
![image](https://github.com/user-attachments/assets/316ab9be-8fed-46b2-ab33-822947b5e3de)

I am running WSL on a Windows 11 machine and downloading it via a simple Curl command:

`curl -fsSL https://ollama.com/install.sh | sh`

![image](https://github.com/user-attachments/assets/67e85a92-0b0a-4ca8-86b7-c43cb10a5cad)

After successful installation. Let's verify and look for flags related to Ollama using below:

``` ollama --help ```

![image](https://github.com/user-attachments/assets/238311f1-192b-4659-bfcb-c81870844847)

## Step 2: Run the First Model

We can go to [https://huggingface.co](https://ollama.com/search) and search for various models. Here I'm searching for llama and it provides me with a different versions of llama model:

![image](https://github.com/user-attachments/assets/7c04d20e-d19b-4b76-9132-4ca9cb3475a7)

We will use llama3.2 with 3 Billion parameters.

![image](https://github.com/user-attachments/assets/3d5eaafc-0bc8-46a0-ac23-198c1d86f795)

To pull this locally on your machine use below command:

`ollama pull llama3.2`

![image](https://github.com/user-attachments/assets/e145a742-60c1-4d52-8543-711dabf0bc79)

Once this is successfully pulled we can verify by listing it using below:

`ollama list`

![image](https://github.com/user-attachments/assets/ae45affa-0d39-400c-926e-38c5153267fe)

Now let's run the model using:

`ollama pull llama3.2`

![image](https://github.com/user-attachments/assets/0783f8b5-e7f9-44d7-ab8a-df31710bd6b0)

Once successful it will show >>> and ask you to send a message as shown above. Once running I have asked the model a following question:
 `suggest 3 ways to generate random and secure passwords` to which I got the following answer:
 
![image](https://github.com/user-attachments/assets/34e3cec7-1563-4872-9eb2-c3823a408457)

## Step 3: Understand the model

`/show info` command will show information on the model in detail which includes things such as:

![image](https://github.com/user-attachments/assets/454e57c1-feb1-459c-986d-dcbf16f3ec76)

- architecture: llama:
  This refers to the model being based on the LLaMA (Large Language Model Meta AI) architecture developed by Meta (Facebook). It’s one of the open-weight large language models known for being efficient and effective.

- parameters: 3.2B
The model has 3.2 billion parameters which are the weights in the neural network that the model uses to learn. More parameters generally mean more capacity to understand and generate complex language — although size isn't everything.

- context length: 131072
This is huge. It means the model can consider up to 131,072 tokens of input text at once. That's roughly equivalent to a full-length novel. Great for long conversations, codebases or documents generation.

- embedding length: 3072
Each token is embedded into a 3072-dimensional vector which is the internal representation the model uses to understand the meaning of words or tokens.

- quantisation: Q4_K_M
This tells us the model has been quantised using a method called Q4_K_M which compresses the model to use less memory and run faster often with minimal loss in accuracy. "Q4" usually means 4-bit quantisation (versus full 16- or 32-bit).

Capabilities: This is what the model can actually do.
- completion: The model supports text completion meaning you can give it a prompt and it will continue it.

- tools: This efers to the ability to interface with external tools such as plugins or APIs. Although exact meaning may depend on your environment.

In short we are using a 3.2B-parameter LLaMA model that's been quantised for speed and has a very long memory and can handle text completions and tool integrations.


