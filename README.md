# RAG-Based Intelligent Document Assistant

## Project Overview

The RAG-Based Intelligent Document Assistant is a document question-answering application that uses Retrieval-Augmented Generation (RAG) to answer user queries based on uploaded PDF documents.

The application extracts text from PDF files, divides the content into smaller chunks, generates embeddings and stores them in ChromaDB. When a user asks a question, the system retrieves relevant document chunks and passes them to the Llama language model to generate context-aware responses.

## Technologies Used

Python, LangChain, LangGraph, Groq API, Google Gemini Embeddings, FAISS, PyPDF, Python Dotenv, Jupyter Notebook.

## Key Features

PDF document loading and text extraction using PyPDF.

Text chunking using Recursive Character Text Splitter.

Semantic embeddings using Google Gemini.

Vector storage and similarity search using FAISS.

Context-based document retrieval.

Answer generation using Groq LLM.

Prompt-based response generation using LangChain.

PDF Documents
      ↓
PDF Text Extraction (PyPDF)
      ↓
Text Chunking
      ↓
Google Gemini Embeddings
      ↓
FAISS Vector Database
      ↓
Semantic Retrieval
      ↓
Context + User Query
      ↓
Groq LLM (GPT-OSS-120B)
      ↓
Context-Aware Answers

## Project Structure
RAG-Document-Assistant/
│
├── data/
│   └── sample.pdf
│
├── notebooks/
│   └── RAG_Document_Assistant.ipynb
│
├── faiss_index/
│
├── requirements.txt
├── README.md
├── .gitignore
└── LICENSE

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/ro-hitk1/RAG-Document-Assistant.git
cd RAG-Document-Assistant
```

### 2. Create a Virtual Environment

```bash
python -m venv .venv
```

Activate the environment:

**Windows:**
```bash
.venv\Scripts\activate
```

**Linux/macOS:**
```bash
source .venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure API Keys

Create a `.env` file in the project root directory and add your API keys:

```env
GOOGLE_API_KEY=your_google_api_key
GROQ_API_KEY=your_groq_api_key
```

Obtain your API keys from:

- Google AI Studio: https://aistudio.google.com/apikey
- Groq Console: https://console.groq.com/keys

### 5. Add PDF Documents

Place your PDF documents inside the `data/` folder.

### 6. Open Jupyter Notebook

```bash
jupyter notebook
```

Open `RAG_Document_Assistant.ipynb` and select your project virtual environment as the Python kernel.

### 7. Execute the Notebook

Run the notebook cells sequentially to load PDFs, generate embeddings, create the FAISS vector database, retrieve relevant content, and generate answers using Groq.

---

## How It Works

1. **PDF Loading:** Load PDF documents and extract their text using PyPDF.
2. **Text Extraction:** Extract and preprocess document content.
3. **Text Chunking:** Divide extracted text into smaller chunks using Recursive Character Text Splitter.
4. **Embedding Generation:** Generate vector embeddings using Google Gemini Embeddings.
5. **Vector Storage:** Store document embeddings in the FAISS vector database.
6. **Semantic Retrieval:** Retrieve the most relevant document chunks based on user queries.
7. **Context Preparation:** Combine retrieved document chunks with the user's question.
8. **Answer Generation:** Pass the context to Groq LLM (GPT-OSS-120B) to generate context-aware answers.

---

## Future Improvements

- Interactive Streamlit web interface.
- Support for additional document formats such as DOCX and TXT.
- Conversation history and multi-turn question answering.
- Improved retrieval techniques and reranking.
- Source attribution with PDF page references.
- RAG evaluation using RAGAS to measure answer quality, faithfulness, and retrieval relevance.
- LangGraph integration for more structured and advanced RAG workflows.

## Author

Rohit Kumar
