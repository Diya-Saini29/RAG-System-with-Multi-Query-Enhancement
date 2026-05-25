RAG System with Multi-Query Enhancement
A beginner-friendly implementation of Retrieval-Augmented Generation (RAG) using local embeddings and FAISS vector search. This project demonstrates both basic RAG and an advanced multi-query fusion approach for improved document retrieval.

📋 Overview
This project implements a complete RAG pipeline that:
Splits documents into manageable chunks
Generates embeddings using sentence-transformers
Builds a FAISS vector index for similarity search
Retrieves relevant context for user queries
Generates answers using a local LLM (DistilGPT2)

🚀 Features
Basic RAG: Single-query retrieval with LLM-based answer generation
Multi-Query RAG: Generates query variations and fuses results for better coverage
Local Processing: Runs entirely offline using open-source models
Visualization: Includes retrieval distance plots and performance metrics

🛠️ Technologies Used
Technology	Purpose
Python 3.12	Core language
Sentence-Transformers	Text embedding generation
FAISS	Vector similarity search
LangChain	Text splitting utilities
Transformers (Hugging Face)	LLM for answer generation
Matplotlib	Data visualization
📦 Installation
bash
pip install langchain sentence-transformers faiss-cpu langchain-community langchain-text-splitters transformers matplotlib
📁 Project Structure
text
rag-project/
├── EL_PROJECT_28APRIL.ipynb   # Main Jupyter notebook
├── README.md                   # This file
└── requirements.txt            # Dependencies (optional)
🔧 How It Works
1. Document Loading
Sample documents about Federated Learning, RAG agents, and multi-modal data curation are loaded.
2. Text Chunking
Documents are split into chunks of ~500 characters with 50-character overlap using RecursiveCharacterTextSplitter.
3. Embedding Generation
The all-MiniLM-L6-v2 model creates 384-dimensional embeddings for each chunk.
4. Vector Indexing
FAISS builds an L2 distance index for fast similarity search.
5. Retrieval & Generation
Basic: Single query → search → LLM generates answer
Advanced: Multiple query variations → search → score-based fusion → LLM generates answer

📊 Key Functions
Function	Description
rag_query(question, k)	Basic RAG retrieval and generation
multi_query_rag(question, k)	Advanced multi-query fusion RAG
🧪 Sample Queries
python
# Basic RAG
answer, context = rag_query("What is RAG?")

# Advanced RAG
answer, queries = multi_query_rag("How does NVIDIA FLARE work?")
📈 Performance Metrics
Hit Rate: 50% on test queries
MRR (Mean Reciprocal Rank): 0.50
Retrieval Time: < 100ms per query
Chunks Created: 4 chunks from 4 source documents

🎯 Learning Outcomes
This project is designed for beginners to understand:
✅ How RAG systems work end-to-end
✅ Text embedding and vector search fundamentals
✅ Query expansion techniques for better retrieval
✅ Integration of retrieval with LLM generation
✅ Evaluation metrics for RAG systems

🔄 Future Improvements
Add support for larger document collections
Implement a better open-source LLM (e.g., Llama 2, Mistral)
Add streaming responses
Build a simple web interface (Gradio/Streamlit)
Implement chunking strategies (semantic chunking)
Add re-ranking for improved accuracy

📚 References
Sentence-Transformers Documentation
FAISS Documentation
LangChain Documentation
RAG Paper (Lewis et al., 2020)

🙏 Acknowledgments
Hugging Face for the all-MiniLM-L6-v2 and distilgpt2 models
Meta FAISS team for the vector search library
