# RAG Document Search System (LangGraph + LangChain + FAISS + Streamlit)

A Retrieval-Augmented Generation (RAG) application that allows users to upload PDFs/text files, search inside them using semantic vector search, and get high-quality answers powered by OpenAI GPT-4o-mini. The system uses LangGraph to orchestrate nodes and includes a ReAct-style agent for optional external knowledge lookup using Wikipedia.

---

## 🚀 Features

### 🔍 **Document Retrieval (RAG)**

* Upload PDF/TXT documents
* Extract text, clean, and chunk
* Generate embeddings using OpenAI
* Store vectors in FAISS for fast similarity search
* Retrieve top-k relevant chunks

### 🧠 **ReAct Agent (Optional Tool Use)**

The system can:

* Use **retriever tool** → fetch relevant chunks
* Use **Wikipedia tool** → get general world knowledge
* Use reasoning steps to decide which tool to call

### 🖥️ **Streamlit UI**

* Upload documents
* Ask questions
* See retrieved context
* View final answer

---

## 📁 Project Structure

```
RAG-Document-search
│   main.py
│   streamlit_app.py
│   requirements.txt
│   pyproject.toml
│   .gitignore
│   .env (not tracked)
│
├── data/
│   ├── attention.pdf
│   └── url.txt
│
└── src/
    ├── config/
    │   ├── config.py
    │   └── __init__.py
    │
    ├── document_ingestion/
    │   ├── document_processor.py
    │   └── __init__.py
    │
    ├── graph_builder/
    │   ├── graph_builder.py
    │   └── __init__.py
    │
    ├── node/
    │   ├── nodes.py
    │   ├── reactnode.py
    │   └── __init__.py
    │
    ├── state/
    │   ├── rag_state.py
    │   └── __init__.py
    │
    └── vectorstore/
        ├── vectorstore.py
        └── __init__.py
```

---

## ⚙️ Installation

### **1. Clone the repository**

```bash
git clone https://github.com/ujwalreddybattu04/RAG-Document-search-project.git
cd RAG-Document-search-project
```

### **2. Create virtual environment (Python 3.12 recommended)**

```bash
python -m venv .venv
.venv\Scripts\activate
```

### **3. Install dependencies**

```bash
pip install -r requirements.txt
```

### **4. Add your API key**

Create a `.env` file:

```
OPENAI_API_KEY=your_openai_api_key
```

---

## ▶️ Running the Application

### **Run the Streamlit UI**

```bash
streamlit run streamlit_app.py
```

The app will open automatically in your browser.

---

## 🧩 How the System Works

### **1. Document Ingestion**

* Extract text from PDF or TXT
* Chunk text into overlapping windows
* Convert chunks into embeddings
* Store vectors in FAISS

### **2. Query Processing**

* User enters a question
* FAISS retrieves top relevant chunks
* System passes chunks + question to the agent

### **3. ReAct Agent Reasoning**

* Chooses between retriever tool or Wikipedia tool
* Produces final natural-language answer

### **4. Streamlit UI displays output**

* Retrieved context
* Final answer

---

## 📦 Technologies Used

| Component     | Technology         |
| ------------- | ------------------ |
| LLM           | OpenAI GPT-4o-mini |
| Orchestration | LangGraph          |
| LLM Framework | LangChain          |
| Vector Store  | FAISS              |
| Embeddings    | OpenAI API         |
| Tools         | Wikipedia API      |
| UI            | Streamlit          |

---

## 🌱 Future Improvements

* Add query rewriting for better retrieval
* Add multi-agent pipeline (validator, summarizer, web-search agent)
* Add support for DOCX + images
* Add conversation memory

---

## 🤝 Contributing

Pull requests are welcome. Please open an issue first if you'd like to discuss major changes.

---

## ⭐ Support

If this project helped you, please **star the repository** on GitHub!
