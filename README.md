# 🎓 CTSE Academic Chatbot

![Chatbot Banner](https://source.unsplash.com/1600x400/?chatbot,ai)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE) [![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/) [![LangChain](https://img.shields.io/badge/LangChain-v0.0.187-green.svg)](https://github.com/langchain/langchain) [![Transformers](https://img.shields.io/badge/Transformers-HuggingFace-orange.svg)](https://github.com/huggingface/transformers) [![FAISS](https://img.shields.io/badge/FAISS-1.7.3-purple.svg)](https://github.com/facebookresearch/faiss)  

---

## 🚀 Project Overview

**CTSE Academic Chatbot** is a domain-specific assistant built to answer student queries using lecture notes from the “Current Trends in Software Engineering” module. By combining a lightweight LLM (GPT-2) with a Retrieval-Augmented Generation (RAG) pipeline, the bot delivers:

- 🎯 **Accurate, context-grounded answers** from PDF lecture materials  
- ⚙️ **Modular, reusable code** in Jupyter Notebook and Python scripts  
- 💡 **Interactive QA** with natural language prompts  

Whether you’re reviewing microservices vs. monoliths, Docker concepts, or CI/CD pipelines, this chatbot provides on-demand academic support tailored to your course content.

---

## 🏗️ Architecture Diagram

```mermaid
flowchart LR
    A[Lecture_Notes.pdf] --> B(PyPDFLoader)
    B --> C[RecursiveCharacterTextSplitter]
    C --> D[MiniLM-L6-v2<br/>Embedding Model]
    D --> E[FAISS Vector DB]
    E -->|search index<br/>top-k chunks| F[FAISS Similarity Search]
    F --> G[Prompt Constructor<br/>(Context + Question)]
    G --> H[GPT-2 Text Generator]
    H --> I[Final Answer]
    I --> J[Chatbot Interface]
