
---

# 💬 AI Mutual Fund Chatbot (RAG-Powered)

An **AI-powered financial chatbot** that answers **mutual fund–related questions** using **Retrieval-Augmented Generation (RAG)**.

It combines:

* ⚙️ **FastAPI backend**
* 🔍 **Vector-based document search**
* 🌐 **React frontend**
* 🤖 **LLM-powered responses**

to deliver a modern, context-aware chat experience.

---

## ⚠️ Disclaimer

> This chatbot **does not provide personalized investment advice**.
> It is intended **for educational purposes only**.

---

## 🚀 Features

* 🤖 **AI-powered financial Q&A**
* 📄 **RAG-based document search** (PDF / text data)
* 🛑 **Guardrails for investment advice**
* 🧠 **Context-aware answers**
* 🗂 **Persistent chat history**
* 🌐 **React-based modern UI**
* 🔒 **Secure API key handling with `.env`**

---

## 🧱 Tech Stack

### Backend (FastAPI)

* **FastAPI** – REST API framework
* **Python** – Core backend language
* **Mistral AI** – LLM for responses
* **RAG (Retrieval Augmented Generation)**
* **Vector Store** – Semantic search over documents
* **python-dotenv** – Environment variable management
* **CORS Middleware** – Frontend integration

### Frontend (React)

* **React (Vite)** – Frontend framework
* **Axios / Fetch** – API communication
* **Modern UI Components**
* **Chat Interface**
* **State Management with Hooks**

---

## 📁 Project Structure

```text
.
├── backend/
│   ├── main.py                # FastAPI application
│   ├── rag/
│   │   ├── vectorstore.py     # Vector search logic
│   ├── chat_history.json     # Chat persistence
│   ├── .env                  # API keys (ignored by git)
│   ├── requirements.txt
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── ChatbotUI.jsx
│   │   │   ├── ChatHeader.jsx
│   │   │   ├── SettingsModal.jsx
│   │   ├── App.jsx
│   │   ├── main.jsx
│   ├── package.json
│   ├── vite.config.js
│
└── README.md
```

---

## 🔍 How RAG Works

1. User asks a question
2. Question is searched in the **vector database**
3. Relevant **document chunks are retrieved**
4. Retrieved context + user query are sent to **Mistral AI**
5. AI responds **grounded in documents**

### 📌 If no relevant document is found:

* The bot answers using **general financial knowledge**
* Clearly mentions that **documents were not used**

---

## 🛑 Investment Advice Guardrails

The chatbot **blocks personalized investment advice**, such as:

* ❌ *“Where should I invest?”*
* ❌ *“Which mutual fund is best?”*
* ❌ *“How much money should I invest?”*

### ✅ Instead, it:

* Explains financial concepts
* Discusses **risk vs return**
* Describes **types of mutual funds**
* Mentions **market trends**

This ensures the app is **safe, compliant, and responsible**.

---

## 🔐 Environment Variables

Create a `.env` file inside `backend/`:

```env
MISTRAL_API_KEY=your_mistral_api_key_here
```

❗ **Never commit `.env` to GitHub**

---

## 🧪 Backend Setup (FastAPI)

### 1️⃣ Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate     # Windows: venv\Scripts\activate
```

### 2️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 3️⃣ Run Server

```bash
uvicorn main:app --reload
```

📍 Server runs at:

```
http://127.0.0.1:8000
```

---

## 🔌 API Endpoints

### Health Check

```http
GET /
```

### Chat Endpoint

```http
POST /chat
```

**Request**

```json
{
  "message": "What is an equity mutual fund?"
}
```

**Response**

```json
{
  "reply": "An equity mutual fund invests primarily in stocks..."
}
```

### Chat History

```http
GET /history
```

---

## 🎨 Frontend Setup (React)

### 1️⃣ Install Dependencies

```bash
cd frontend
npm install
```

### 2️⃣ Start React App

```bash
npm run dev
```

📍 App runs at:

```
http://localhost:5173
```

---

## 🔗 Frontend → Backend Connection

Example API call:

```javascript
fetch("http://127.0.0.1:8000/chat", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ message: userMessage }),
});
```

---

## 📚 Chat History

* Stored in `chat_history.json`
* Last **50 conversations** retained
* Automatically saved on every chat

---

## 🧠 Model Configuration

* **Model:** `mistral-small`
* **Temperature:** `0.2` (low hallucination, high accuracy)
* **Context-aware responses**

---

## 🚧 Future Improvements

* 🔐 Authentication
* 📊 User-specific chat history
* 📁 PDF upload from UI
* 🔎 Advanced document filtering
* ☁️ Cloud deployment (Docker / Hugging Face / AWS)

---

## ⚠️ Final Disclaimer

> This chatbot does **not provide financial advice**.
> Always consult a **SEBI-registered financial advisor** before making investment decisions.

---

## 👨‍💻 Author

**Karthik Kallapiran**
AI • Full-Stack • RAG Systems

---


