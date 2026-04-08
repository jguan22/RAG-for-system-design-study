# System Design RAG Tutor 🤖🏛️

A Retrieval-Augmented Generation (RAG) system built to assist in studying high-scale system design. This tool parses technical documentation, engineering blogs, and study notes to provide grounded, detailed architectural advice using the Google Gemini 2.5 API.

## 🚀 Features
- **Header-Aware Chunking:** Intelligently splits Markdown files by headers (`#`, `##`, `###`) to maintain architectural context and metadata.
- **Semantic Vector Search:** Utilizes `ChromaDB` and the `all-MiniLM-L6-v2` transformer model to find relevant study materials by meaning rather than just keywords.
- **Advanced LLM Integration:** Powered by **Gemini 2.5 Flash** for high-speed, senior-engineer-level reasoning and interview-style feedback.
- **Persistent Storage:** Local vector database saves your indexed documents, so you only need to ingest data once.

## 🛠️ Tech Stack
- **Environment Manager:** [uv](https://docs.astral.sh/uv/)
- **LLM:** Google Gemini 2.5 Flash
- **Vector Database:** ChromaDB
- **Embeddings:** `all-MiniLM-L6-v2` (Sentence-Transformers)
- **Language:** Python 3.12+

## 📋 Prerequisites
Ensure you have `uv` and `Jupyter` installed. 
- **uv:** [Installation Guide](https://docs.astral.sh/uv/getting-started/installation/)
- **Jupyter:** `uv tool install jupyterlab --with jupyterlab-lsp`

## ⚙️ Setup

1. **Clone the repository:**
   ```bash
   git clone <your-repo-url>
   cd system-design-rag
   ```

2. **Configure Environment Variables:**
Create a .env file in the root directory and add your API key:

    ```bash
    GEMINI_API_KEY=your_google_gemini_api_key
    ```

    Note: Obtain your key from Google AI Studio.

3. **Install Dependencies:**

    ```bash
    uv add sentence_transformers chromadb google-genai python-dotenv
    ```

4. **Prepare Data:**

    Place your study materials (e.g., Alex Xu notes, System Design Primer, Tech Blogs) as .md files into the /data folder.

## 🏃 Method of Operation

1. **Launch Jupyter Lab:**

    ```bash
    uv run --with jupyter jupyter lab
    ```

2. **Ingestion:**

    Run the ingestion cells to parse headers, generate embeddings, and populate the ChromaDB collection.

3. **Query:**

    Use the ask_system_design_expert function to simulate a mock interview or clarify complex distributed systems concepts.

## 📂 Project Structure

```bash
.
├── data/               # Source Markdown files for study
├── system_design_db/   # Persistent ChromaDB vector storage
├── .env                # Private API credentials (ignored by git)
├── .gitignore          # Prevents leaking .env and DB files
└── main.ipynb          # Core RAG logic and chat interface
```

## ⚖️ License
MIT License - Feel free to use this for your own SDE interview preparation!
