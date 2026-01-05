# 🧠 Autism RAG Chatbot (Arabic)

A **document-grounded Retrieval-Augmented Generation (RAG) chatbot** specialized in **Autism Spectrum Disorder (ASD)**.  
The system answers user questions **strictly based on uploaded Arabic PDF documents**, using persistent vector storage to prevent hallucinations and ensure reliable responses.

---

## 📌 Project Overview

This project implements an **Arabic-friendly RAG pipeline** that:
- Extracts and cleans Arabic text from PDF files
- Splits documents into semantic chunks
- Generates multilingual embeddings
- Stores embeddings persistently using ChromaDB
- Retrieves relevant context at query time
- Generates answers using modern LLMs (**GPT-4o-mini / Gemini**)

The chatbot **never answers from general knowledge** — only from the provided documents.

---

## 🏗️ System Architecture

PDF Documents
↓
Text Extraction & Cleaning
↓
Smart Chunking (+ Overlap)
↓
Multilingual Embeddings (E5)
↓
Persistent Chroma Vector Store
↓
Similarity Search (Top-K)
↓
LLM (GPT-4o-mini / Gemini)
↓
Grounded Answer


---

## 📂 Project Structure

```text
Arabic-RAG-Chatbot/
│
├── 01_autism_pdf_ingestion.ipynb        # PDF extraction, cleaning, and chunking
├── 02_autism_vectorstore_build.ipynb    # Embedding generation & ChromaDB persistence
├── 03_autism_rag_inference.ipynb        # RAG inference (question answering)
│
├── autism_rag_inference.py              # Standalone inference script
├── requirements.txt
└── README.md
🧪 Key Features
✅ Arabic text normalization

✅ Persistent vector storage (no re-embedding)

✅ Multilingual semantic search

✅ Hallucination control

✅ Google Drive persistence (Colab-friendly)

✅ Supports GPT-4o-mini and Gemini models

⚙️ Technologies Used
Python

LangChain

ChromaDB

Sentence Transformers

HuggingFace Embeddings (multilingual-e5-large)

OpenAI GPT-4o-mini

Google Gemini

Google Colab

🚀 How to Run
1️⃣ Build the Dataset
Run:

01_autism_pdf_ingestion.ipynb
2️⃣ Build the Vector Store
Run:

02_autism_vectorstore_build.ipynb
This step is done once only.

3️⃣ Ask Questions
Run:

03_autism_rag_inference.ipynb
Or execute:

python autism_rag_inference.py
🧠 Example Query
User:

ما هي النصائح العملية للتعامل مع نوبات الغضب؟

System Behavior:

Retrieves relevant document chunks

Generates an answer only from the retrieved context

Refuses to hallucinate if information is missing

⚠️ Important Notes
The embedding model must remain the same during build and inference.

If no relevant information is found, the chatbot explicitly states that.

This project is designed for educational and research purposes.

🎓 Academic Use
This project is suitable for:

AI & NLP coursework

Information Retrieval

Software Engineering projects

Ethics-aware AI systems

📜 License
This project is provided for educational use only.

✨ Author
Developed as an academic RAG-based AI system focused on Autism Spectrum Disorder and Arabic-language resources.
