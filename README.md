# 🧠 AI RAG Chatbot & Email Responder Workflow in n8n

This project showcases a production-style **Retrieval-Augmented Generation (RAG)** pipeline built using [n8n](https://n8n.io). It demonstrates how businesses can ingest documents and power AI-driven customer support across both **chat** and **email**.

---

## 📦 Features

- **Google Drive Integration** – Upload a new file and trigger document ingestion.
- **Document Vectorization** – Uses OpenAI to generate embeddings from policy/FAQ files.
- **Vector Store with Pinecone** – Stores chunks of content in a semantic search engine.
- **Chat-Based Q&A (Chatbot)** – Users can ask natural language questions and receive AI-generated answers using RAG logic.
- **AI Agent Integration** – Combines memory, tools, and models for richer multi-turn interactions.
- **Email-Based Auto-Reply** – Automatically responds to user policy questions submitted via email using the same RAG pipeline.

---

## 📁 Workflow Structure

```text
1. Document Ingestion & Indexing
   └── Google Drive Trigger → Download File → Pinecone Upload
                          ↘→ Default Data Loader → Text Splitter → Embeddings → Pinecone Store

2. Chatbot Interaction
   └── Chat Message Trigger → OpenRouter Chat Model → AI Agent → Pinecone Tool

3. Email-Based Responder
   └── Email Trigger → Extract Email Text → Pinecone Search → LLM (or mock) → Email Reply
```

---

## 📝 Files

- `rag_chatbot_workflow.json` – Full exported n8n workflow including both chatbot and email responder
- `policy_document.pdf` – Sample policy file used for vector generation

---

## 🚀 How to Use

1. Open [n8n](https://n8n.io) (self-hosted or cloud)
2. Import this JSON workflow
3. Add your:
   - OpenAI or OpenRouter key
   - Pinecone API key and index
   - Google Drive and Email credentials
4. Upload a file to Google Drive to trigger vectorization
5. Ask a question via:
   - Manual chat trigger
   - Sending an email to the connected inbox


