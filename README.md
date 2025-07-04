# 🧠 EmpathAI: A RAG-Powered Therapy Companion

EmpathAI is a local Retrieval-Augmented Generation (RAG) chatbot that simulates a compassionate therapy assistant. It uses psychological guides (Cognitive Behavioral Therapy [CBT] techniques) and your past emotional entries to offer supportive, emotionally intelligent responses, all without uploading your data to the cloud.

> 💬 “How you feel matters. EmpathAI helps you put it into words.”

---

## 🧩 Features

- 🔍 **Retrieval-Augmented Generation (RAG)**: Combines document knowledge + personal memory to generate informed replies.
- 🧠 **Emotion Detection**: Automatically deduces your feelings from input ("I feel stuck") using LLM inference.
- 📚 **Therapy Guides**: Built-in CBT, mindfulness, and grounding techniques, chunked and embedded for context-aware retrieval.
- 🗂️ **Persistent Memory**: All user interactions are saved and reloaded on future sessions.
- 🎨 **Gradio Interface**: Clean, conversational UI for local or remote interaction.
- 🛡️ **Offline-Compatible**: No cloud data storage; all memory and documents live in your local environment or Google Drive.

---

## 🛠️ Technologies Used

- **Google Gemini API** (via `google-generativeai`)
- **FAISS** for similarity search and vector indexing
- **Sentence-Transformers** (`all-MiniLM-L6-v2`) for text embeddings
- **Gradio** for web-based chat UI
- **Google Colab + Drive** integration for easy use and persistence

---

## 📁 Project Structure
-EmpathAI/
│
├── cbt_docs/ # Folder of therapy text files (.txt)
├── therapy_logs.json # Memory log of past user inputs + emotions
├── memory.index # FAISS vector index (therapy + memory)
├── memory_chunks.txt # All stored text chunks (therapy + logs)
├── empathai.ipynb # Main Colab Notebook
└── README.md

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/EmpathAI.git
cd EmpathAI

### 2. Upload Therapy Docs

Put your `.txt` therapy techniques inside the `cbt_docs/` folder.  
Each file should cover one concept (e.g., `grounding.txt`, `cognitive_reframing.txt`, etc.).

---

### 3. Run in Google Colab

Open `empathai.ipynb` in Google Colab and run all cells in order:

- ✅ Mount Google Drive  
- ✅ Load or initialize the FAISS index  
- ✅ Interact with the chatbot via the Gradio interface  

You can also modify the interface to run with Streamlit or a local Flask app.

---

## 💡 How It Works

- Therapy documents and past logs are split into chunks and embedded with `sentence-transformers`.
- All embeddings are stored in a FAISS index.
- When you type a message:
  1. The app **deduces your feeling**
  2. Logs it to `therapy_logs.json`
  3. Adds it to the FAISS vector index
  4. Retrieves top-k relevant memory + guide chunks
  5. Feeds them to **Gemini** to generate a supportive response
- The full conversation appears in the Gradio UI.

---

## 🧪 Example Use

> **User:** I feel like everything is spiraling and I can't catch my breath  
> **EmpathAI:** It sounds like you’re experiencing intense anxiety. Let’s try the _Grounding Technique_ together. Focus on 5 things you can see...

---

## 🧾 License

**MIT License** — free for personal, academic, or commercial use.  
Attribution appreciated but not required.

---

## 🤝 Contributing

Want to improve EmpathAI? Contributions are welcome!

- 🧠 Add new therapy techniques  
- 🧪 Enhance emotional classification  
- 🔍 Improve RAG chunking or retrieval  
- 🧩 Add local/offline LLM support

---

## 📬 Contact

**Mohamad ali Oussayli** — AI Engineer & Creator  
📧 moussayli2004@gmail.com

---

> _EmpathAI doesn’t replace therapy, but it can be a daily check-in for your mental well-being._
