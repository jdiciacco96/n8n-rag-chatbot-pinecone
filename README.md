# AI Knowledge Base Chatbot

A Retrieval-Augmented Generation (RAG) chatbot built with n8n, OpenAI, Pinecone, Google Drive, and OpenRouter.

This project automatically ingests documents from Google Drive, generates vector embeddings using OpenAI, stores them in Pinecone, and allows users to query the knowledge base through an AI-powered chatbot.

---

## Overview

This project consists of two connected workflows:

### 1. Knowledge Ingestion Pipeline

Automatically monitors a Google Drive folder for new documents.

When a file is added:

1. The Google Drive Trigger detects a new document.
2. The document is downloaded.
3. Content is extracted using the Default Data Loader.
4. Text is split into smaller chunks using a Recursive Character Text Splitter.
5. OpenAI Embeddings generates vector representations of each chunk.
6. Embeddings are stored in a Pinecone Vector Store.

This creates a searchable vector database that can be queried by an AI agent.

---

### 2. RAG Chatbot Workflow

When a user submits a message:

1. The AI Agent receives the user question.
2. The Pinecone Vector Store performs semantic similarity search.
3. Relevant document chunks are retrieved.
4. Claude Sonnet 4.5 (via OpenRouter) receives both the user question and retrieved context.
5. The model generates a grounded response based on the knowledge base.

This allows the chatbot to answer questions using uploaded documents instead of relying solely on pretrained model knowledge.

---

## Technologies Used

- n8n
- OpenAI Embeddings
- Pinecone Vector Database
- OpenRouter
- Claude Sonnet 4.5
- Google Drive API
- Retrieval-Augmented Generation (RAG)
- Semantic Search
- Vector Embeddings
- AI Agents

---

## Workflow Architecture

### Document Ingestion Pipeline

```text
Google Drive Trigger
           │
           ▼
     Download File
           │
           ▼
  Default Data Loader
           │
           ▼
 Recursive Text Splitter
           │
           ▼
   OpenAI Embeddings
           │
           ▼
 Pinecone Vector Store
```

### AI Chatbot Workflow

```text
User Question
       │
       ▼
    AI Agent
       │
       ▼
 Generate Embedding
       │
       ▼
 Pinecone Similarity Search
       │
       ▼
 Retrieve Context
       │
       ▼
 Claude Sonnet 4.5
       │
       ▼
 Generated Response
```

---

## Features

- Automated document ingestion
- Google Drive integration
- Intelligent document chunking
- OpenAI vector embeddings
- Pinecone vector database storage
- Semantic similarity search
- Retrieval-Augmented Generation (RAG)
- Context-aware chatbot responses
- Low-code AI workflow automation
- AI Agent architecture

---

## Example Questions

The AI Assistant can answer questions such as:

```text
What hiring models are available?

How are candidates evaluated?

What technical skills are most commonly requested?

What industries hire through the platform?

Can startups use the platform?

What is Retrieval-Augmented Generation (RAG)?

Why use a vector database?

Why are startups using AI agents?

How can n8n be used inside an organization?

What technologies are commonly used by modern startups?

What is the difference between semantic search and keyword search?

Why are embeddings important for AI applications?
```

### Example Response Scenarios

The chatbot can answer questions related to:

- Remote hiring and technical recruiting
- Software engineering teams
- AI agents and workflow automation
- Startup operations
- Semantic search
- Retrieval-Augmented Generation (RAG)
- Vector databases
- Embeddings
- Knowledge management systems
- Modern software development
- n8n workflow automation
- Technical best practices

---

## How It Works

### Document Processing

Documents uploaded to Google Drive are automatically:

- Downloaded
- Parsed into text
- Split into smaller chunks
- Converted into embeddings
- Stored in Pinecone

### Semantic Search

Instead of searching keywords directly, the chatbot:

- Converts questions into embeddings
- Searches Pinecone for similar content
- Retrieves the most relevant context
- Passes context to the AI model

This allows the chatbot to understand meaning rather than exact word matches.

---

## What I Learned

This project provided hands-on experience with:

- Retrieval-Augmented Generation (RAG)
- Pinecone Vector Databases
- OpenAI Embeddings
- n8n Workflow Development
- AI Agent Architecture
- OpenRouter Model Integration
- Semantic Search
- Document Processing Pipelines
- Knowledge Base Systems
- Prompt Engineering
- Event-Driven Automation
- Low-Code AI Development

---

## Future Improvements

- Conversation memory
- Response citations
- Multi-document indexing
- Metadata filtering
- Supabase vector storage implementation
- User authentication
- Web-based user interface
- Agent analytics and observability
- Multi-agent architecture
- Hybrid search (keyword + semantic search)

---

## Repository Structure

```text
ai-knowledge-base-chatbot/
│
├── workflows/
│   └── RAG Pipeline & Chatbot.json
│
├── docs/
│   ├── Arc_Tech_Startup_FAQ.docx
│   └── sample-knowledge-base.docx
│
├── screenshots/
│   └── workflow.png
│
└── README.md
```

---

## Importing Into n8n

1. Open n8n
2. Click **Import Workflow**
3. Upload the JSON workflow file
4. Configure credentials:
   - Google Drive
   - OpenAI
   - Pinecone
   - OpenRouter
5. Activate the workflow

---

## Repository Description

```text
AI-powered RAG chatbot built with n8n, Pinecone, OpenAI embeddings, and Claude Sonnet. Automatically ingests documents from Google Drive and answers questions using semantic search and retrieval-augmented generation.
```

---

## GitHub Topics

```text
n8n
rag
pinecone
openai
embeddings
vector-database
semantic-search
ai-agent
chatbot
automation
openrouter
claude
knowledge-base
llm
```

---

## Author

Built as part of a hands-on exploration of AI agents, vector databases, semantic search, and Retrieval-Augmented Generation (RAG) using n8n.
