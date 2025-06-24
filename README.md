# 📊 RAG Agent for Stock Market Analysis using Google Gemini 2.0

This project is an intelligent Retrieval-Augmented Generation (RAG) agent designed to interact with stock market performance data provided in PDF format. It combines vector-based retrieval with Google's Gemini 2.0 Flash model to answer natural language questions grounded in document evidence.

---

## 🚀 Features

- 📄 Extracts and semantically chunks text from PDF documents
- 🔍 Embeds and stores chunks in a persistent Chroma vector store
- 🧠 Uses LangChain to build a tool-aware agent loop with state memory
- 🤖 Answers user queries using Gemini 2.0 Flash model + document retrieval
- 🔁 Multi-step reasoning over retrieved chunks

---

## 🛠️ Tech Stack

- `LangChain` for agent and retrieval orchestration
- `ChromaDB` for vector storage
- `PyPDFLoader` to parse and extract text from PDFs
- `GoogleGenerativeAI` for LLM (Gemini 2.0 Flash) and embeddings (`embedding-001`)
- `LangGraph` to implement a tool-invoking agent loop

---

## 📂 Project Structure


---

## ⚙️ Setup Instructions(bash commands)

1. Clone the repository 
   git clone https://github.com/arkapratimdnath/RAG-Agent.git
   cd RAG-Agent
2. Install dependencies
   pip install -r requirements.txt
3. Set up your .env file
   GOOGLE_API_KEY=your_google_generative_ai_key
4. Place your PDF in the root directory
5. Run the agent
   python app.py

🧠 Agent Logic Flow
1. The user enters a question.
2. Gemini 2.0 Flash model checks if document retrieval is needed.
3. If needed, the agent calls the retriever tool.
4. The retrieved documents are summarised by Gemini and presented as an answer.
