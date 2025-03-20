# Advanced News Article Chat Bot

A sophisticated RAG (Retrieval Augmented Generation) system that processes and analyzes Microsoft's annual report using advanced NLP techniques. This project demonstrates the power of combining document processing, embedding generation, and visualization to create an intelligent document analysis system.

## Features

- PDF document processing and text extraction
- Advanced text chunking using both character and token-based splitting
- Vector database integration using ChromaDB
- Sentence transformer embeddings for semantic search
- Query augmentation using GPT-3.5-turbo
- UMAP dimensionality reduction for embedding visualization
- Interactive visualization of document embeddings and query results

## Prerequisites

- Python 3.x
- OpenAI API key
- Required Python packages (see requirements.txt)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/<repository-url>
cd adv-news-article-chat-bot
```

2. Install the required packages:
```bash
pip install -r requirements.txt
```

3. Create a `.env` file in the root directory and add your OpenAI API key:
```
OPENAI_API_KEY=your_api_key_here
```

## Project Structure

- `expansion_answer.py`: Main script containing the RAG implementation
- `helper_utils.py`: Utility functions for embedding projection and text formatting
- `data/`: Directory containing the PDF documents
- `.env`: Environment variables configuration

## Usage

1. Place your PDF document in the `data/` directory (currently configured for "microsoft-annual-report.pdf")

2. Run the main script:
```bash
python expansion_answer.py
```

The script will:
- Process the PDF document
- Generate embeddings for the text chunks
- Store them in a ChromaDB collection
- Process queries and visualize the results

## How It Works

1. **Document Processing**:
   - Extracts text from PDF pages
   - Filters empty strings
   - Splits text into manageable chunks using both character and token-based splitting

2. **Embedding Generation**:
   - Uses SentenceTransformer for generating embeddings
   - Stores embeddings in ChromaDB for efficient retrieval

3. **Query Processing**:
   - Takes user queries
   - Augments queries using GPT-3.5-turbo for better context
   - Retrieves relevant document chunks based on semantic similarity

4. **Visualization**:
   - Uses UMAP for dimensionality reduction
   - Creates interactive visualizations showing:
     - Document embeddings (gray points)
     - Retrieved documents (green circles)
     - Original query (red X)
     - Augmented query (orange X)

## Dependencies

- openai
- pypdf
- chromadb
- sentence-transformers
- umap-learn
- matplotlib
- python-dotenv
- langchain