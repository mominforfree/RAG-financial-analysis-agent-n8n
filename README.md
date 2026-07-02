# Financial PDF RAG Agent with n8n

A RAG-based financial document analysis agent built using **n8n**, **Pinecone**, **Google Drive**, and **OpenAI**.

This project allows an AI agent to answer questions from a financial PDF by retrieving relevant document chunks from Pinecone before generating a response.

---

## Project Overview

This project contains two n8n workflows:

1. **PDF Ingestion to Pinecone**
   - Downloads a financial PDF from Google Drive
   - Loads and extracts PDF text
   - Splits the document into chunks
   - Generates embeddings using OpenAI
   - Stores vectors in Pinecone

2. **RAG Financial Analysis Agent**
   - Receives user questions through chat
   - Searches relevant PDF chunks from Pinecone
   - Uses OpenAI to generate grounded answers
   - Avoids guessing when information is not found in the PDF

---

## Tech Stack

- n8n
- OpenAI
- Pinecone
- Google Drive
- RAG
- Vector Database
- AI Agent

---

## Architecture

```text
Google Drive PDF
        ↓
n8n Ingestion Workflow
        ↓
PDF Loader
        ↓
Text Splitter
        ↓
OpenAI Embeddings
        ↓
Pinecone Vector Database
        ↓
n8n RAG Agent Workflow
        ↓
AI Agent + Pinecone Retrieval
        ↓
Final Answer