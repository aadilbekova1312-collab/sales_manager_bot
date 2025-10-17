# sales_manager_bot
AI-powered Telegram bot for sales managers. Built with n8n, OpenAI, Supabase, and a Google Drive-based RAG knowledge system.

Overview

1️⃣ `bot_config.json`
Main Telegram bot workflow:
- Handles incoming Telegram messages  
- Uses OpenAI GPT-4o for responses  
- Connects to Supabase for chat logs and vector storage  
- Retrieves answers from the RAG database (Google Drive embeddings)  
- Sends alerts to the admin if the bot lacks information  

**Tech stack:**
- Telegram API  
- Supabase  
- OpenAI (GPT-4o / GPT-4o-mini)  
- PostgreSQL memory  
- n8n LangChain nodes  
---
2️⃣ `google_drive_loader.json`
Automated pipeline that syncs Google Drive documents with the Supabase vector database.

Workflow:
- Watches a specific Google Drive folder
- Downloads new/updated files  
- Converts Docs, Sheets, Slides → PDF  
- Extracts text and splits into chunks  
- Embeds text with OpenAI embeddings  
- Uploads chunks into Supabase `documents` table  

**Tech stack:**
- Google Drive Trigger  
- LangChain Embeddings + Text Splitter  
- Supabase VectorStore  
---
🧾 License
MIT License — open for educational and research use.  
© 2025 Gulnur GV / Aigerim Adilbekova

⚠️ All sensitive keys and IDs are masked for security reasons.
