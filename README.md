 # 🎯 RAG YouTube Transcript Q&A with LangChain

> **Retrieval-Augmented Generation** pipeline that allows you to **ask questions about YouTube videos** using their transcripts.  
> Powered by **LangChain**, **OpenAI GPT models**, and **YouTube Transcript API**.

---

## 📌 Overview

This project takes a **YouTube video** → extracts its transcript → breaks it into chunks → stores embeddings in a **FAISS** vector store → retrieves relevant content based on a query → and finally uses an **LLM** to answer your question **only from the transcript**.

 

---

## 🚀 Features

✅ **Automatic Transcript Fetching** (supports multiple error cases)  
✅ **Chunking for Long Transcripts** using `RecursiveCharacterTextSplitter`  
✅ **Vector Search** with FAISS for fast retrieval  
✅ **Augmented GPT Answers** strictly from the video transcript  
✅ **Runnable Chains** with LangChain’s modular pipeline  
✅ **Custom Prompt Template** to ensure factual accuracy from transcript  

---

## 🛠️ Tech Stack

- **LangChain** – RAG pipeline framework  
- **YouTube Transcript API** – Transcript extraction  
- **OpenAI GPT Models** – Question answering (`gpt-4o-mini`)  
- **FAISS** – Vector search  
- **Python** – Core programming language  

---

## 📂 Project Structure

rag_using_langchain.ipynb 

# Main project notebook
README.md     # Project documentation

---

## ⚙️ Installation

1️⃣ **Clone the repository**  
```bash
git clone  https://github.com/24f2000164/RAG-YouTube-Video-Summarizer-.git
cd  RAG-Youtube_Video-Summarizer-

2️⃣ Install dependencies

 
pip install youtube-transcript-api langchain langchain_openai langchain_community faiss-cpu

3️⃣ Set OpenAI API Key

---
export OPENAI_API_KEY="your_api_key_here"  # Mac/Linux
setx OPENAI_API_KEY "your_api_key_here"    # Windows


▶️ Usage
1. Set the YouTube Video ID
 
video_id = "bSDprg24pEA"  # Replace with your own


2. Run Transcript Retrieval
 
from youtube_transcript_api import YouTubeTranscriptApi
transcript_list = YouTubeTranscriptApi.get_transcript(video_id, languages=["en"])

3. Ask Questions
 
main_chain.invoke("Who is Demis?")
main_chain.invoke("Can you summarize the video?")
main_chain.invoke("Is nuclear fusion discussed?")

🧠 Example Output
Query:

 
Is the topic of nuclear fusion discussed in this video?
Answer:

Yes, the speaker discusses nuclear fusion in the context of future energy solutions, highlighting its potential benefits and challenges.

🛡 Error Handling
TranscriptsDisabled → "Captions disabled for this video."

NoTranscriptFound → "No English captions available."

Other Errors → Prints full exception details

🔮 Future Improvements
🌍 Multi-language support

💾 Store multiple videos in the same FAISS index

⚡ API deployment with FastAPI or Flask

📊 Visualization of transcript search results

🤝 Contributing
Pull requests are welcome!
If you find a bug or have a feature request, open an issue.

📜 License
MIT License © 2025 — Sahil kumar

💡 This project is a great starting point for building custom Q&A systems for any video content using Retrieval-Augmented Generation.


 