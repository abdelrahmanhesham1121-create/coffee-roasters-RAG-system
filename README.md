# ☕ Aetherium RAG System with Supabase, Google Gemini, & n8n

An end-to-end Retrieval-Augmented Generation (RAG) system built to answer enterprise support queries for **Aetherium Coffee Roasters** using vector embeddings and LLM reasoning.

## 🏗️ Tech Stack

- **Orchestration:** n8n Workflow
- **Vector Database:** Supabase (PostgreSQL + `pgvector`)
- **Embeddings Model:** Google Gemini Embeddings (`gemini-embedding-001` / `text-embedding-004`)
- **LLM Engine:** Google Gemini Chat Model (`gemini-1.5-flash`)

## 🚀 Getting Started

### 1. Database Setup (Supabase)
1. Go to your Supabase SQL Editor.
2. Run the script provided in `supabase/schema.sql` to enable `pgvector`, create the `document_chunks` table, and register the `match_documents` RPC function.

### 2. Data Ingestion
1. Upload the knowledge base file in `docs/aetherium_company_docs.md`.
2. Chunk the text using Recursive Character Text Splitter (Chunk Size: 500, Overlap: 50).
3. Generate embeddings and store them inside Supabase.

### 3. Import n8n Workflow
1. Open n8n.
2. Go to **Workflows** -> **Import from File**.
3. Select `n8n/workflow.json`.
4. Configure your Supabase Credentials and Google Gemini API Key.

## 📄 License
MIT
