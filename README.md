# Document_QA_chatbot_RAG
# 🤖 PDF Chatbot with RAG, MMR Search & Mistral (Ollama)

An intelligent **Conversational AI assistant** that lets you chat with PDF documents. Powered by:
- 🔍 **MMR-based Retrieval + Reranking**
- 🧠 **Mistral-7B (Ollama)** for both Q&A and summarization
- 🧾 Dynamic **max_tokens allocation**
- 🗃️ Contextual memory with **LangChain’s ConversationBufferMemory**
- ⚙️ Reliable **streaming with error fallback**

---

## 🚀 Features

- 🧠 **Chat with PDFs** – Ask questions or get summaries from any uploaded document
- 🔄 **MMR Search** – Uses Maximal Marginal Relevance to balance relevance and diversity in retrieval
- 🧠 **LangChain Memory** – Keeps track of recent chat context (last 3–5 turns)
- 📈 **Dynamic Token Budgeting** – Adjusts output length based on input size (supports large PDFs)
- 💬 **Streaming LLM Output** – Real-time answers with error handling fallback
- 💻 **Runs locally** with Ollama (no API keys needed!)

---

## 🧰 Tech Stack

| Component       | Technology                                      |
|----------------|--------------------------------------------------|
| LLM            | [`mistral`](https://ollama.com/library/mistral) via [Ollama](https://ollama.com) |
| Embeddings     | `sentence-transformers/all-MiniLM-L6-v2`         |
| Vector Store   | FAISS                                            |
| Tokenizer      | HuggingFace Transformers                         |
| Retrieval      | MMR + Cross-Encoder Reranking                    |
| Memory         | LangChain `ConversationBufferMemory`            |

---


## 🧪 Example Interaction
```markdown
Choose mode - 'qna', 'summary', 'clear', 'show history', 'exit': qna

💬 Ask your question: What’s the main objective of the document?

🤖 The primary objective of the report is to explore the role of AI in streamlining operational workflows across industries...

Choose mode: summary

📄 Summary:  
This document discusses the growing influence of AI, emphasizing its applications in predictive analytics, efficiency optimization...

```


## 📌 Notes

- Ensure that the **Ollama server is running** in the background before starting the application.
- Open a **separate terminal window** and run the following command:
  
  ```
  ollama run mistral
  ```

- 🟣 If it’s your first time using the model, this command will download and start the Mistral model locally.  
- 📘 Keep this terminal window open while using the app, as it communicates with the running Ollama server.  
- 💡 Avoid closing the terminal running Ollama, or the chatbot application will stop responding.
