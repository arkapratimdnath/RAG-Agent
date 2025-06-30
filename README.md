# 📊 RAG Agent for Stock Market Analysis using Google Gemini 2.0

An intelligent Retrieval-Augmented Generation (RAG) agent that answers natural language questions about stock market performance data from PDF reports. It combines vector-based retrieval with Google's Gemini 2.0 Flash model to provide evidence-grounded, multi-step answers.

---

## 🚀 Features

- 📄 Extracts and semantically chunks text from PDF documents
- 🔍 Embeds and stores chunks in a persistent Chroma vector store
- 🧠 Uses LangChain and LangGraph to build a tool-aware agent loop with state memory
- 🤖 Answers user queries using Gemini 2.0 Flash model + document retrieval
- 🔁 Supports multi-step reasoning over retrieved chunks
- 📝 Always cites the specific document parts used in answers

---

## 🛠️ Tech Stack

- **LangChain**: Agent and retrieval orchestration
- **ChromaDB**: Vector storage
- **PyPDFLoader**: PDF parsing and text extraction
- **GoogleGenerativeAI**: LLM (Gemini 2.0 Flash) and embeddings (`embedding-001`)
- **LangGraph**: Tool-invoking agent loop

---

## 📂 Directory Structure

```
arkapratimdnath-rag-agent/
├── README.md
├── app.py
├── requirements.txt
├── Stock_Market_Performance_2024.pdf
└── 1baf1ea8-d4dc-4794-8a79-eed5ce52470f/   # ChromaDB persistence files
```

---

## ⚙️ Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/arkapratimdnath/RAG-Agent.git
cd RAG-Agent
```

2. **Install dependencies**

```bash
pip install -r requirements.txt
```

3. **Set up your `.env` file**

Create a `.env` file in the root directory and add your Google API key:

```env
GOOGLE_API_KEY=your_google_generative_ai_key
```

4. **Add your PDF**

Place your stock market PDF (e.g., `Stock_Market_Performance_2024.pdf`) in the project root.

5. **Run the agent**

```bash
python app.py
```

---

## 🧠 Agent Logic Flow

1. The user enters a question.
2. Gemini 2.0 Flash model checks if document retrieval is needed.
3. If needed, the agent calls the retriever tool to fetch relevant PDF chunks.
4. Retrieved documents are summarized and cited in the answer.
5. The process can repeat for multi-step reasoning.

---

## 💻 Example Usage

```shell
$ python app.py

=== RAG AGENT===

What is your question: What was the best performing sector in Q1 2024?

=== ANSWER ===
Document 2:
[Relevant excerpt from the PDF...]

The best performing sector in Q1 2024 was Technology, as shown in Document 2 above.
```

Type `exit` or `quit` to stop the agent.

---

## 📝 Notes & Troubleshooting

- The PDF file **must** be named `Stock_Market_Performance_2024.pdf` and placed in the root directory (or update the path in `app.py`).
- The ChromaDB persistence directory is set to the project root by default.
- If you encounter `FileNotFoundError`, check your PDF filename and location.
- Requires a valid Google Generative AI API key.

---

## 📦 Requirements

```
langgraph
langchain
langchain-google-genai
dotenv
langchain_chroma
langchain_community
pypdf
```

---
