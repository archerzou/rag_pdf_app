# RAG PDF Application

A powerful Retrieval-Augmented Generation (RAG) application that enables intelligent question-answering over PDF documents using Large Language Models.

## 🌟 Features

- **PDF Upload & Processing**: Upload and process PDF documents for intelligent querying
- **Vector Search**: Efficient semantic search using embeddings
- **Real-time Q&A**: Ask questions and receive context-aware answers from your documents
- **Source Attribution**: View the source document and location for each answer
- **Interactive UI**: Clean and intuitive Streamlit interface
- **Asynchronous Processing**: Fast document processing with Inngest workflow engine

## 🏗️ Architecture

This application consists of three main components:

1. **FastAPI Backend** (`main.py`): RESTful API for document management and querying
2. **Inngest Worker**: Asynchronous background processing for PDF ingestion
3. **Streamlit Frontend** (`streamlit_app.py`): User-friendly interface for interaction

## 🚀 Getting Started

### Prerequisites

- Python 3.9+
- uv (Python package manager)
- Node.js and npx (for Inngest CLI)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/archerzou/rag_pdf_app.git
   cd rag_pdf_app
   ```

2. **Install dependencies**
   ```bash
   uv sync
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   OPENAI_API_KEY=your_openai_api_key_here
   # Add other necessary API keys
   ```

### Running the Application

You'll need to run three services simultaneously. Open three terminal windows:

#### Terminal 1: FastAPI Backend
```bash
uv run uvicorn main:app --reload
```
The API will be available at `http://127.0.0.1:8000`

#### Terminal 2: Inngest Worker
```bash
npx inngest-cli@latest dev -u http://127.0.0.1:8000/api/inngest --no-discovery
```

#### Terminal 3: Streamlit Frontend
```bash
uv run streamlit run streamlit_app.py
```
The UI will be available at `http://localhost:8501`

## 📖 Usage

1. **Upload a PDF**
   - Navigate to the Streamlit interface
   - Use the file uploader to select your PDF document
   - Wait for the document to be processed and indexed

2. **Ask Questions**
   - Type your question in the chat input
   - The system will retrieve relevant context from the document
   - Receive an answer with source attribution

3. **View Sources**
   - Each answer includes references to the source document
   - Click on source links to see where the information came from

## 🛠️ Technology Stack

- **Backend Framework**: FastAPI
- **Frontend**: Streamlit
- **Workflow Engine**: Inngest
- **LLM Provider**: OpenAI
- **Vector Database**: [Specify your vector DB - e.g., Pinecone, Chroma, FAISS]
- **Embeddings**: [Specify your embedding model]
- **PDF Processing**: [Specify library - e.g., PyPDF2, pdfplumber]

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

