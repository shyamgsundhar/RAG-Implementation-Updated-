# 📚 RAG-PDF Assistant
![Developer](https://img.shields.io/badge/👨‍💻_Developer-Shyam_Sundhar_G-1e90ff?style=for-the-badge&logo=github&logoColor=white)


[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)  
[![FAISS](https://img.shields.io/badge/vector_search-FAISS-green)](https://github.com/facebookresearch/faiss)  
[![Google Gemini](https://img.shields.io/badge/LLM-Gemini-orange)](https://ai.google.dev/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A **Retrieval-Augmented Generation (RAG) system** that lets you **chat with your PDF documents** using **FAISS** for vector search and **Google Gemini** for embeddings & text generation.  

This project extracts text from PDFs, creates embeddings, stores them in a **vector database**, and allows you to ask natural language questions. The system retrieves the most relevant chunks and generates context-aware answers.

---

## 🔎 What is RAG?

**Retrieval-Augmented Generation (RAG)** is an AI framework that combines:
1. **Retrieval** – Searching a knowledge base (vector database) for the most relevant information.  
2. **Generation** – Using a Large Language Model (LLM) to produce human-like answers *based on retrieved data*.  

💡 This ensures the model:
- Reduces **hallucinations** (making up facts).  
- Provides **context-aware** and **document-grounded** answers.  
- Allows querying **private/custom data** not seen during training.  

---

## 🏛️ A Short History of RAG

- **Pre-2020**: LLMs were used as standalone systems (GPT-2, GPT-3 early days). They generated fluent but often *unreliable* outputs.  
- **2020 (Meta/Facebook AI)**: RAG was introduced in the paper *"Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks"*.  
- **Today**: RAG powers tools like **ChatGPT with browsing**, **Gemini with docs**, **Microsoft Copilot**, etc.  

---

## ⚙️ Why RAG for PDFs?

PDFs are often **large, unstructured, and dense** (books, research papers, legal docs, reports).  
RAG helps by:
- Splitting them into **chunks**.  
- Embedding chunks into **vectors**.  
- Searching for relevant parts when you ask a question.  
- Generating accurate answers with **citations to page numbers**.  

---

## 📂 Project Flow

```

📄 PDF Document
↓
Text Extraction (PyPDF2)
↓
Chunking (500 chars each)
↓
Embeddings (Gemini API)
↓
Vector Database (FAISS)
↓
Question (User Input)
↓
Query Embedding + Similarity Search
↓
Retrieve Top Chunks (Context)
↓
Gemini LLM Generates Answer
↓
Answer with References (Page numbers)

````

---

## 🚀 Features

- ✅ Extracts text from **any PDF**  
- ✅ **Chunks text** for efficient retrieval  
- ✅ Uses **Google Gemini** embeddings & LLMs  
- ✅ Stores vectors with **FAISS**  
- ✅ Interactive **Q&A chatbot** with your document  
- ✅ Provides **page references** in answers  
- ✅ Saves & reloads vector database (`.index` + `.pkl`)  

---

## 📦 Installation

1. **Clone repository**  
```bash
git clone https://github.com/yourusername/rag-pdf-assistant.git
cd rag-pdf-assistant
````

2. **Install dependencies**

```bash
pip install faiss-cpu google-generativeai PyPDF2 numpy
```

3. **Set your Gemini API key**

```bash
export GEMINI_API_KEY="your_api_key_here"   # Linux/Mac
setx GEMINI_API_KEY "your_api_key_here"     # Windows
```

---

## 🛠️ Usage

### Step 1: Convert PDF → Vectors

```bash
python pdf_to_vectors.py
```

* Extracts text from `doc.pdf`
* Creates embeddings with Gemini
* Stores data in:

  * `vectors.index` (FAISS index)
  * `chunks.pkl` (text chunks + metadata)

### Step 2: Ask Questions

```bash
python ask_questions.py
```

Example session:

```
🤖 RAG System Ready! Ask me questions about your PDF
💡 Type 'bye' to exit
====================================================

Your question: What is the main conclusion of the paper?
Searching and generating answer...
Answer: The document concludes that RAG significantly improves factual accuracy compared to standalone LLMs. [Page 12]
```

---

## 📊 Applications

* 📖 **Education** – Summarize textbooks, answer questions from lecture notes.
* ⚖️ **Legal** – Query contracts, case studies, compliance docs.
* 💊 **Healthcare** – Search medical research papers or patient records.
* 📈 **Business** – Analyze reports, financial statements, whitepapers.
* 🔬 **Research** – Summarize and cross-reference academic papers.

---

## 🌟 Advantages

* **Accuracy**: Less hallucination, grounded answers.
* **Scalability**: Works with large documents.
* **Flexibility**: Any PDF → knowledge base.
* **Transparency**: Mentions page references.
* **Efficiency**: Fast retrieval with FAISS.

---

## 📌 Example Questions You Can Ask

* "Summarize the introduction in 3 sentences."
* "What are the limitations discussed in the paper?"
* "Give me the equations mentioned in section 2."
* "Where does the author mention deep learning?"

---

## 🔮 Future Improvements

* 🔍 Support **multi-PDF search**
* 🗂️ Advanced **chunking by sections/tables**
* 🖼️ Extract **images/figures with OCR**
* 🌐 Deploy as a **web app** (Flask/Streamlit)
* 🔒 Add **user authentication & private storage**

---

## 🤝 Contributing

Pull requests are welcome!
Please open an issue first to discuss major changes.

---

