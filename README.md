# AI Evals for RAG

This project is an end-to-end evaluation framework for a Retrieval-Augmented Generation (RAG) system.  
It evaluates whether a RAG pipeline retrieves the right context, generates relevant answers, and avoids hallucinations.

The system uses AI/ML research papers as the knowledge source, retrieves relevant document chunks using FAISS, generates answers using GPT-4o, and evaluates the results using both human scoring and automated DeepEval metrics.

## Project Overview

RAG systems are useful only when they can produce answers that are accurate and grounded in source documents.  
This project focuses on evaluating the quality of a RAG pipeline instead of only building a chatbot.

The evaluation answers three main questions:

1. Did the retriever find the right context?
2. Did the LLM answer the user’s question correctly?
3. Is the answer faithful to the retrieved context?

## Key Features

- Extracts text from AI/ML research papers
- Splits documents into meaningful chunks
- Creates embeddings using Sentence Transformers
- Stores embeddings in a FAISS vector database
- Retrieves top relevant chunks for each query
- Generates answers using GPT-4o
- Creates a benchmark set of evaluation questions
- Supports human annotation with 1–5 scoring
- Uses DeepEval to evaluate:
  - Answer Relevancy
  - Contextual Relevancy
  - Faithfulness
- Compares baseline prompt performance with improved prompt performance
- Saves evaluation results into CSV files for analysis

## Tech Stack

- Python
- FAISS
- Sentence Transformers
- OpenAI GPT-4o
- DeepEval
- PyMuPDF
- Pandas
- NumPy

## How It Works

The pipeline follows these steps:

```text
Research Papers
      ↓
Text Extraction
      ↓
Document Chunking
      ↓
Embedding Generation
      ↓
FAISS Vector Store
      ↓
Question Set / Golden Queries
      ↓
Context Retrieval
      ↓
Answer Generation
      ↓
Human + Automated Evaluation
      ↓
Prompt Improvement and Re-evaluation
