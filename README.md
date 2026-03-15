# RAG Developement

Starter repository for experimenting with Retrieval-Augmented Generation (RAG) workflows using local documents, vector stores, and notebook-based exploration.

The project currently looks like an early research sandbox: the main application code is still minimal, while most of the work appears to happen in notebooks and data pipelines. This README is written to help you or any collaborator get the project running quickly and understand the current structure.

## What This Project Covers

- Document ingestion from sources like PDF, Excel, CSV, and text files
- Text chunking and preprocessing for retrieval
- Embedding generation with `sentence-transformers` and LangChain integrations
- Vector storage experiments with FAISS and Chroma
- LLM integrations through OpenAI and Groq
- Search experimentation with Typesense
- Notebook-driven prototyping for agentic RAG flows

## Current Status

Right now the repo is in a prototype stage.

- `main.py` is only a placeholder entry point
- most implementation work appears to be inside notebooks
- `src/` is present but mostly empty
- `data/` already contains source folders and a `vector_store` directory

That means this repo is best treated as a research and development workspace rather than a production-ready package.

## Tech Stack

- Python 3.11+
- LangChain ecosystem
- LangGraph
- OpenAI
- Groq
- Hugging Face embeddings
- FAISS
- ChromaDB
- Typesense
- Pandas
- PyMuPDF / PyPDF
- Unstructured

## Project Structure

```text
rag-developement/
|-- data/
|   |-- csv/
|   |-- excel/
|   |-- pdf/
|   |-- text_files/
|   `-- vector_store/
|-- notebooks/
|-- src/
|   `-- __init__.py
|-- agenticrag.ipynb
|-- typesense.ipynb
|-- main.py
|-- pyproject.toml
|-- requirements.txt
`-- README.md
```

## Setup

### 1. Clone the repository

```powershell
git clone https://github.com/your-username/agentic-rag-lab.git
cd agentic-rag-lab
```

### 2. Create and activate a virtual environment

PowerShell:

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

Using `uv`:

```powershell
uv sync
```

If you prefer using the requirements file:

```powershell
uv add -r requirements.txt
```

Or with `pip`:

```powershell
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root with the keys you plan to use:

```env
OPENAI_API_KEY=your_openai_api_key
GROQ_API_KEY=your_groq_api_key
TYPESENSE_API_KEY=your_typesense_api_key
TYPESENSE_HOST=your_typesense_host
TYPESENSE_PORT=443
TYPESENSE_PROTOCOL=https
```

## Running the Project

At the moment, the Python entry point is only a stub:

```powershell
python main.py
```

Expected output:

```text
Hello from rag-developement!
```

For actual experimentation, open the notebooks:
- `1. document.ipynb`
- `agenticrag.ipynb`
- `typesense.ipynb`

## Suggested Workflow

1. Put your source documents into the relevant `data/` folders.
2. Use the notebooks to load and preprocess documents.
3. Split text into chunks.
4. Generate embeddings.
5. Store embeddings in FAISS, Chroma, or another vector index.
6. Query the retriever and connect the results to an LLM.
7. Compare retrieval quality and response quality across setups.

## Data Layout

The current `data/` directory is organized by source type:

- `data/pdf/` for PDF files
- `data/excel/` for Excel files
- `data/csv/` for CSV files
- `data/text_files/` for plain text files
- `data/vector_store/` for saved vector indexes or retrieval artifacts

## Notebooks
### `1. document.ipynb`
Start with this NoteBook

### `agenticrag.ipynb`

Intended for experimenting with agentic or iterative RAG patterns, likely involving retrievers, tool-like steps, and LLM orchestration.

### `typesense.ipynb`

Intended for testing Typesense-backed indexing or search workflows.

## Dependencies of Interest

Some important libraries already included:

- `langchain`, `langchain-core`, `langchain-community`
- `langchain-openai`
- `langchain-groq`
- `langchain-huggingface`
- `langgraph`
- `sentence-transformers`
- `faiss-cpu`
- `chromadb`
- `typesense`
- `unstructured`

## Roadmap Ideas

If you want to turn this into a cleaner project, good next steps would be:

- move notebook logic into reusable modules under `src/`
- add a proper ingestion pipeline
- create a retriever abstraction for multiple vector stores
- add evaluation scripts for retrieval quality
- add `.env.example`
- add tests for loaders, chunking, and retrieval
- build a CLI or API entry point

## Important Security Note

Never commit real API keys to the repository. Keep secrets in `.env`, add `.env` to `.gitignore`, and rotate any keys that may already have been exposed.

## License

Add a license here if you plan to share or open-source the project.
