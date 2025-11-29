# Generative AI Email Search System
An intelligent generative AI search system for email corpus analysis using **LangChain**, **OpenAI**, and **ChromaDB**.

## Overview

Semantic Spotter is a email search and analysis system that helps organizations find, validate, and analyze decisions, strategies, and data buried in massive email archives. Using advanced generative AI and multiple specialized agents, it transforms raw email data into actionable business intelligence.

## Key Features

### **Components**
- **Email Parser**: Processes raw email data from CSV format
- **Chunking Engine**: Splits emails into semantic chunks with overlap
- **Embedding Generator**: Creates vector representations using OpenAI
- **Vector Store**: ChromaDB for efficient similarity search
- **LangChain Agent**: Orchestrates retrieval and generation
- **Query Engine**: Handles user queries and returns contextual answers

### **AI-Powered Intelligence**
- **OpenAI Integration**: GPT-3.5-turbo.
- **Natural Language Processing**: Understanding complex email search queries
- **Context Awareness**: Maintains conversation history and preferences
- **Intelligent Routing**: Automatic function selection based on user intent

### **Agents**:
- **Conversational Agent**: Natural conversation with memory
  - **Features**:
    - Maintains conversation history
    - Context-aware responses
    - Friendly, natural interaction
    - References previous questions  
- **Data Analytics Agent**: Statistical analysis and data insights
  - **Features**:
    - Pandas-based analytics
    - Natural language to Python code
    - Descriptive statistics
    - Data aggregation and grouping
- **SQL Agent**: Structured database queries
   - **Features**:
     - SQL query to Natural language
     - Complex joins and filters
     - Database schema understanding
     - Efficient structured queries

## Architecture

The system consists of four main layers:

1. **Data Ingestion Layer**: Email parsing and preprocessing
2. **Embedding Layer**: Vector embeddings using OpenAI
3. **Storage Layer**: ChromaDB vector database
4. **Agent Layer**: LangChain-powered intelligent search

## 🚀 Quick Start

### Prerequisites
```bash
1. Python 3.11+
2. 16GB RAM (minimum 8GB)
3. GPU access recommended (but not required)
4. OpenAI API key
5. Kaggle account (for dataset access)
```

### Installation
```bash
pip install -U -qq langchain==0.3 langchain-openai==0.3 \
  langchain_community==0.3 langchain-experimental==0.3 chromadb
```

### Quick Demo
```bash
# Clone or download the notebook
# Copy email-search-agent.ipynb to your environment

# 1. Load and index emails (one-time setup, ~15 minutes)
emails = load_emails_batch()  # Loads 517,401 emails
email_df = pd.DataFrame(emails)

# 2. Initialize agent
interactive_multi_agent_mode()

## Interactive Mode Commands
| Command | Description | Available In |
|---------|-------------|--------------|
| `/mode [agent]` | Switch agent (conv\||analytics\|sql) | All modes |
| `/info` | Show agent information | All modes |
| `/history` | Show conversation history | Conversational only |
| `/exit` | Exit system | All modes |

## Agent Selection Guide
Use Conversational Agent when:
  - Having a multi-turn conversation
  - Need context from previous questions
  - Want natural, friendly interaction

Use Analytics Agent when**:
  - Need statistical insights
  - Want to analyze patterns
  - Performing data aggregation
  - Calculating metrics

Use SQL Agent when:
  - Need precise structured queries
  - Filtering by specific fields
  - Counting and grouping
  - Joining related data
  
## Database Schema
The SQL agent creates the following tables:

emails:
  - file_ref (TEXT) - Email file reference
  - message_id (TEXT) - Unique message ID
  - date (TEXT) - Email date
  - from (TEXT) - Sender email
  - to (TEXT) - Recipient email
  - subject (TEXT) - Email subject
  - cc (TEXT) - CC recipients
  - bcc (TEXT) - BCC recipients
  - folder (TEXT) - Email folder
  - origin (TEXT) - Email origin
  - body (TEXT) - Email body

senders:
  - sender_id (INTEGER) - Unique sender ID
  - from (TEXT) - Sender email

recipients
  - recipient_id (INTEGER) - Unique recipient ID
  - to (TEXT) - Recipient email

```


## Usage Examples

### CONVERSATIONAL AGENT
Switch: ```/mode conv```
```text
# User Query: "I'm looking for emails about business meetings or travel plans."
# Agent: Absolutely! To help narrow down the search for emails related to business meetings or travel plans, could you provide me with any specific keywords or details related to those topics? For example, if you remember any particular dates, names of attendees, or destinations mentioned in the emails, that would be helpful for me to find the relevant information. Feel free to share any additional details, and I'll do my best to assist you in locating the specific emails. Let's work together to find the information you need!
```

### ANALYTICS AGENT
Switch: ```/mode analytics```
```text
# User Query: "What is the average email body length?"
# Agent: The average email body length is approximately 1826.85 characters.
```

### SQL AGENT
Switch: ```/mode sql```
```text
# User SQL Query: "SELECT COUNT(*) AS total_emails FROM emails;"
# Agent: Total Email Count - 517401
```

### Pro Tips for Interactive Mode
```text
# Switch agents quickly
/mode conv    # Conversational
/mode analytics  # Stats  
/mode sql     # Structured

# Get help
/info         # Available Agents info
/history      # Provides Conversational history
```

## Data Sources

### Enron Email Dataset (517K entries)
```
https://www.kaggle.com/datasets/wcukierski/enron-email-dataset/data
```

```text
file,message
allen-p/_sent_mail/1.,"Message-ID: <123@enron.com>
Date: Mon, 14 May 2001 09:45:00 -0700
From: phillip.allen@enron.com
To: john.lavorato@enron.com
Subject: California Forecasts

This is the email body content..."
```


## Troubleshooting

### Common Issues

#### "OpenAI API Key Not Found"
```bash
# add to your text file
OpenAI_API_Key.txt
```

## Technology Stack

- **Framework**: LangChain 0.3
- **LLM**: OpenAI GPT-3.5-turbo
- **Embeddings**: OpenAI text-embedding-ada-002(1536 dims)
- **Vector Store**: ChromaDB(embedded)
- **Database**: SQLite
- **Analytics**: Pandas

## Conclusion

**Email Search Agent** is an generative AI system that enables intelligent semantic search and analysis of large email archives. Built with LangChain 0.3, OpenAI GPT-3.5-turbo, and ChromaDB, this system processes and indexes 517,401 emails from the Enron dataset, providing sophisticated multi-agent capabilities for conversational Q&A, SQL queries, data analytics, and complex reasoning.

## Acknowledgments
- This project was inspired by Upgrad IIIT Bangalore PG program on ML and AI.
- This project was based on LangChain

## Contact
Created by @[GVChalamaReddy](https://github.com/GVChalamaReddy) - feel free to contact me!
---

