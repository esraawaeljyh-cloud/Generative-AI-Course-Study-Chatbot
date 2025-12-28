# Generative-AI-Course-Study-Chatbot

This project implements a **study chatbot** for the *Generative AI* course.  
The chatbot answers questions **strictly based on the provided course slides** using **Retrieval-Augmented Generation (RAG)** to ensure accuracy and prevent hallucinations.

---

## Project Overview

The chatbot is designed to help students review and study Generative AI concepts by:
- Retrieving relevant content from course slides (PDFs)
- Generating concise, grounded answers
- Refusing to answer questions that are not covered in the course material

The system combines **LangChain**, **FAISS**, **Hugging Face embeddings**, and an **LLM via OpenRouter**, with a **Gradio-based user interface**.

---

## Key Features

- 📚 **Course-grounded answers only** (no outside knowledge)
- 🧠 **Retrieval-Augmented Generation (RAG)** using FAISS
- ❌ Explicit response when information is not found:
  > *"I don't know based on the course material."*
- 📄 **Source citation** (file name & page number) for each valid answer
- 🛡️ Reduced hallucinations via strict prompt design
- 💬 Simple and user-friendly **Gradio GUI**

---

## Technologies Used

- **Python**
- **LangChain (LCEL)**
- **FAISS** (Vector Store)
- **Hugging Face Embeddings**
  - `sentence-transformers/all-MiniLM-L6-v2`
- **OpenRouter API**
  - Model: `mistralai/mistral-7b-instruct`
- **Gradio** (Web Interface)
- **PyPDF** (PDF loading)

---

## System Architecture

1. **Course Slides (PDFs)** are loaded as documents  
2. Text is split into chunks using `RecursiveCharacterTextSplitter`  
3. Chunks are embedded and stored in **FAISS**  
4. Relevant chunks are retrieved for each question  
5. The LLM generates answers **only from retrieved context**  
6. Answers include **source and page number** when applicable  

---

## Installation & Setup

### 1. Install Dependencies

```bash
pip install -U langchain langchain-community langchain-text-splitters
pip install -U faiss-cpu sentence-transformers
pip install -U transformers gradio
pip install -U langchain-openai pypdf
