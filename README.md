# Generative-AI-Course-Study-Chatbot

This project implements a **study chatbot** for the Generative AI course using **Retrieval-Augmented Generation (RAG)**.  
The chatbot answers questions **only based on the course slides** and avoids using any external knowledge.

---

## Overview

The chatbot loads the course PDFs, splits them into text chunks, stores them in a vector database, and retrieves the most relevant content to answer user questions accurately.

If the answer is not found in the course material, the chatbot responds with:  
**"I don't know based on the course material."**

---

## Technologies Used

- Python  
- LangChain (LCEL)  
- FAISS (Vector Store)  
- Hugging Face Embeddings  
- Mistral 7B via OpenRouter  
- Gradio (Web Interface)

---

## How It Works

1. Load course slides (PDFs)
2. Split text into chunks
3. Create embeddings and store them in FAISS
4. Retrieve relevant chunks for each question
5. Generate answers strictly from retrieved content
6. Display answers using a Gradio interface

---

## How to Run

1. Install the required libraries
2. Add course PDF files to the `data/` folder
3. Set your OpenRouter API key
4. Run the notebook and use the Gradio interface to ask questions

---

## Purpose

This project demonstrates how **RAG improves answer accuracy and reduces hallucinations** compared to a plain LLM when working with educational content.

