System Design RAG Tutor 🤖🏛️
A Retrieval-Augmented Generation (RAG) system built to assist in studying high-scale system design. This tool parses technical documentation, engineering blogs, and study notes to provide grounded, detailed architectural advice using the Google Gemini 2.5 API.

🚀 Features
Header-Aware Chunking: Intelligently splits Markdown files by headers to maintain architectural context.

Vector Search: Utilizes ChromaDB and sentence-transformers for semantic retrieval of study materials.

Advanced LLM Integration: Powered by Gemini 2.5 Flash for high-speed, senior-engineer-level reasoning.

Persistent Storage: Local vector database to save and query indexed documents across sessions.

🛠️ Tech Stack
Environment Manager: uv

LLM: Google Gemini 2.5 Flash

Vector Database: ChromaDB

Embeddings: all-MiniLM-L6-v2 (Sentence-Transformers)

Language: Python 3.12+ / Jupyter Lab

📋 Prerequisites
Ensure you have uv installed. If not, refer to the installation guide.

⚙️ Setup
Clone the repository:

Bash
git clone <your-repo-url>
cd system-design-rag
Configure Environment Variables:
Create a .env file in the root directory:

Plaintext
GEMINI_API_KEY=your_google_gemini_api_key
Get your key at Google AI Studio.

Install Dependencies:

Bash
uv add sentence_transformers chromadb google-genai python-dotenv
Prepare Data:
Place your study materials (e.g., Alex Xu notes, System Design Primer, Tech Blogs) as .md files into the /data folder.

🏃 Method of Operation
Launch Jupyter Lab:

Bash
uv run --with jupyter jupyter lab
Ingestion: Run the ingestion cells to parse headers, generate embeddings, and populate the ChromaDB collection.

Query: Use the ask_system_design_expert function to simulate a mock interview or clarify complex distributed systems concepts.

📂 Project Structure
Plaintext
├── data/               # Source Markdown files for study
├── system_design_db/   # Persistent ChromaDB vector storage
├── .env                # Private API credentials (ignored by git)
├── .gitignore          # Prevents leaking .env and DB files
└── main.ipynb          # Core RAG logic and chat interface
⚖️ License
MIT License - Feel free to use this for your own SDE interview preparation!