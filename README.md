# ⚖️ Legal AI Advisor

**An AI-powered legal document assistant that understands your uploaded documents and answers your questions using Retrieval-Augmented Generation (RAG).**

Legal AI Advisor is an intelligent document-based question-answering system that allows users to upload legal documents, ask questions in natural language, and receive context-aware answers grounded in the provided content.

Instead of relying solely on an LLM's pre-trained knowledge, the system retrieves relevant information from uploaded documents and uses it to generate accurate, contextual responses.

## 🚀 Key Features

- **Document-Based Question Answering:** Upload legal documents and ask questions directly related to their content.
- **Retrieval-Augmented Generation (RAG):** Combines document retrieval with LLM-based response generation to provide context-aware answers.
- **FAISS Vector Database:** Stores and retrieves relevant document chunks efficiently using semantic similarity search.
- **Semantic Search:** Understands the meaning and context of queries rather than relying only on exact keyword matches.
- **Context-Aware Responses:** Generates answers using retrieved document passages as supporting context.
- **Interactive Interface:** Provides a user-friendly interface through Streamlit for uploading documents and interacting with the AI assistant.
- **Legal Information Assistance:** Helps users understand legal clauses, provisions, definitions, and other information contained in their uploaded documents.

## 🛠️ Technology Stack

| Component | Technologies |
|---|---|
| Programming Language | Python |
| Frontend | Streamlit |
| LLM Integration | Groq API |
| LLM | Llama-based language models |
| RAG Framework | Retrieval-Augmented Generation |
| Vector Database | FAISS |
| Embeddings | Sentence Transformers / Embedding Models |
| Document Processing | PDF processing and text extraction |
| Data Handling | JSON, Python |

## 🧠 How It Works

The application follows a Retrieval-Augmented Generation pipeline:

1. **Document Upload:** Users provide legal documents (PDFs and supported text sources).
2. **Text Extraction:** The system extracts textual content from the uploaded documents.
3. **Text Chunking:** Extracted content is divided into smaller, manageable chunks to improve retrieval accuracy.
4. **Embedding Generation:** Each chunk is converted into a numerical vector representation using an embedding model.
5. **Vector Storage:** Generated embeddings are stored in a FAISS vector index.
6. **Query Processing:** When a user asks a question, the query is converted into an embedding.
7. **Similarity Search:** FAISS retrieves the most relevant document chunks based on semantic similarity.
8. **LLM-Based Generation:** Retrieved context is passed to the language model, which generates a relevant response grounded in the available documents.

### Architecture

```text
         User
          |
          v
   Upload Legal Documents
          |
          v
    Text Extraction
          |
          v
      Text Chunking
          |
          v
   Embedding Generation
          |
          v
     FAISS Vector Store
          |
          |
     User Query
          |
          v
    Query Embedding
          |
          v
   Semantic Similarity Search
          |
          v
   Retrieve Relevant Chunks
          |
          v
   LLM (Groq API)
          |
          v
  Context-Aware Answer
          |
          v
      User Interface
```

## 📂 Project Structure

```text
LEGAL-AI-ADVISOR/
│
├── app.py
├── frontend.py
├── rag_pipeline.py
├── vector_database.py
├── finetune.py
├── constitution_qa.json
├── requirements.txt
├── .gitignore
│
├── pdfs/
│   └── Legal PDF documents
│
├── vectorstore/
│   └── faiss_index/
│       ├── index.faiss
│       └── index.pkl
│
└── README.md
```

## ⚙️ Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/bhavi1608/LEGAL-AI-ADVISOR.git
cd LEGAL-AI-ADVISOR
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it:

**Windows:**
```bash
venv\Scripts\activate
```

**Linux / macOS:**
```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure API Key

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key
```

Never commit your `.env` file or expose your API key publicly.

### 5. Run the Application

If using the Streamlit frontend:

```bash
streamlit run frontend.py
```

If your application uses a different entry point, run the corresponding Streamlit command.

## 💡 Example Use Cases

- Upload the Constitution of India and ask questions about fundamental rights.
- Understand specific legal provisions and clauses.
- Retrieve relevant information from multiple uploaded legal documents.
- Ask questions about definitions, obligations, and legal terminology.
- Explore complex legal documents through natural-language queries.

## 🔮 Future Improvements

- Support for additional document formats such as DOCX and TXT.
- Improved retrieval using hybrid search and reranking.
- Source citations with page numbers and document references.
- Multi-document comparison and summarization.
- Conversation history and persistent user sessions.
- Improved response evaluation and hallucination detection.

## ⚠️ Disclaimer

Legal AI Advisor is an informational and educational tool designed to assist users in understanding legal documents. It does not provide professional legal advice and should not replace consultation with a qualified legal professional. Responses depend on the quality and availability of the uploaded documents.

## 👩‍💻 Author

**Bhavya Gauttam**

[GitHub](https://github.com/bhavi1608)

---

*Making legal information more accessible through Retrieval-Augmented Generation and AI.*
