```markdown
# 💬 Mutualfund Chat – RAG-Powered AI Assistant

An AI-powered chatbot built to answer **mutual fund–related questions** using **Retrieval-Augmented Generation (RAG)**.  
The system combines a **FastAPI backend**, **semantic vector search**, and a **modern React-based chat interface** to deliver accurate, contextual, and responsible financial explanations.

> ⚠️ **Disclaimer**  
> This application is for **educational purposes only** and does **not provide personalized investment advice**.

---

## 🖼️ Application Screenshots

### Chat Interface
![Mutualfund Chat UI](screenshots/chat-ui.png)

### Landing Page
![Mutualfund Chat Landing Page](screenshots/landing-page.png)

---

## 🚀 Features

- 🤖 AI-powered mutual fund Q&A  
- 📄 RAG-based document retrieval (PDF / text sources)  
- 🧠 Context-aware, document-grounded answers  
- 🛑 Guardrails against personalized investment advice  
- 🗂 Persistent chat history  
- 🌐 Modern and responsive chat UI  
- 🔒 Secure API key handling using environment variables  

---

## 🧱 Tech Stack

### Backend (FastAPI)

- FastAPI – REST API framework  
- Python – Core backend language  
- Mistral AI – Large Language Model  
- Retrieval-Augmented Generation (RAG)  
- Vector Store – Semantic document search  
- dotenv – Environment variable management  
- CORS Middleware – Frontend integration  

### Frontend (React)

- React (Vite) – Frontend framework  
- Fetch / Axios – API communication  
- Modern UI components  
- Chat-based interface  
- State management with React Hooks  

---

## 📁 Project Structure

```

.
├── backend/
│   ├── main.py                # FastAPI application
│   ├── rag/
│   │   ├── vectorstore.py     # Vector search logic
│   ├── chat_history.json     # Persistent chat history
│   ├── .env                  # API keys (git ignored)
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
├── screenshots/
│   ├── chat-ui.png
│   ├── landing-page.png
│
└── README.md

```

---

## 🔍 How Retrieval-Augmented Generation Works

1. The user submits a query  
2. The query is searched in the vector database  
3. Relevant document chunks are retrieved  
4. Retrieved context is combined with the user query  
5. The LLM generates a grounded response  

**Fallback behavior**  
If no relevant documents are found, the chatbot responds using general financial knowledge and clearly states that documents were not used.

---

## 🛑 Investment Advice Guardrails

The chatbot intentionally blocks questions such as:

- “Which mutual fund should I invest in?”  
- “Where should I put my money?”  
- “How much should I invest?”  

Instead, it focuses on:
- Explaining financial concepts  
- Discussing risk vs return  
- Describing mutual fund categories  
- Sharing general market insights  

This ensures responsible and compliant usage.

---

## 🔐 Environment Variables

Create a `.env` file inside the `backend/` directory:

```

MISTRAL_API_KEY=your_mistral_api_key_here

````

Do not commit the `.env` file to version control.

---

## 🧪 Backend Setup (FastAPI)

### Create Virtual Environment
```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
````

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Run the Server

```bash
uvicorn main:app --reload
```

Backend runs at:

```
http://127.0.0.1:8000
```

---

## 🔌 API Endpoints

### Health Check

```
GET /
```

### Chat

```
POST /chat
```

Request:

```json
{
  "message": "What is an equity mutual fund?"
}
```

Response:

```json
{
  "reply": "An equity mutual fund primarily invests in stocks..."
}
```

### Chat History

```
GET /history
```

---

## 🎨 Frontend Setup (React)

### Install Dependencies

```bash
cd frontend
npm install
```

### Start Development Server

```bash
npm run dev
```

Frontend runs at:

```
http://localhost:5173
```

---

## 📚 Chat History

* Stored in `chat_history.json`
* Last 50 conversations retained
* Automatically updated after every message

---

## 🧠 Model Configuration

* Model: `mistral-small`
* Temperature: `0.2` (low hallucination, higher accuracy)
* Context-aware responses

---

## 🚧 Planned Enhancements

* 🔐 Authentication
* 📊 User-specific chat history
* 📁 PDF upload from UI
* 🔎 Advanced document filtering
* ☁️ Cloud deployment (Docker / Hugging Face / AWS)

---

## ⚠️ Disclaimer

This application does **not provide financial advice**.
Consult a **SEBI-registered financial advisor** before making investment decisions.

---

## 👨‍💻 Author

**Karthik Kallapiran**
AI • Full-Stack • RAG Systems

```
```
