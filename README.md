💬 AI Mutual Fund Chatbot (RAG-Powered)

An AI-powered financial chatbot that answers mutual fund–related questions using Retrieval-Augmented Generation (RAG).
It combines a FastAPI backend, vector-based document search, and a React frontend for a modern chat experience.

⚠️ Disclaimer:
This chatbot does not provide personalized investment advice. It is for educational purposes only.

🚀 Features

🤖 AI-powered financial Q&A

📄 RAG-based document search (PDF / text data)

🛑 Guardrails for investment advice

🧠 Context-aware answers

🗂 Persistent chat history

🌐 React-based modern UI

🔒 Secure API key handling with .env

🧱 Tech Stack
Backend (FastAPI)

FastAPI – REST API framework

Python – Core backend language

Mistral AI – LLM for responses

RAG (Retrieval Augmented Generation)

Vector Store – Semantic search over documents

dotenv – Environment variable management

CORS Middleware – Frontend integration

Frontend (React)

React (Vite) – Frontend framework

Axios / Fetch – API calls

Modern UI Components

Chat Interface

State Management with Hooks

📁 Project Structure
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

🔍 How RAG Works Here

User asks a question

Question is searched in the vector database

Relevant document chunks are retrieved

Retrieved context + user query are sent to Mistral

AI responds grounded in documents

If no relevant document is found:

The bot answers using general financial knowledge

Clearly mentions that documents were not used

🛑 Investment Advice Guardrails

The chatbot blocks personalized investment advice, such as:

“Where should I invest?”

“Which mutual fund is best?”

“How much money should I invest?”

Instead, it:

Explains concepts

Discusses risk vs return

Describes types of mutual funds

Mentions market trends

This keeps the app safe, compliant, and responsible.

🔐 Environment Variables

Create a .env file inside backend/:

MISTRAL_API_KEY=your_mistral_api_key_here


❗ Never commit .env to GitHub.

🧪 Backend Setup (FastAPI)
1️⃣ Create Virtual Environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Run Server
uvicorn main:app --reload


Server will run at:

http://127.0.0.1:8000

🔌 API Endpoints
Health Check
GET /

Chat Endpoint
POST /chat


Request

{
  "message": "What is an equity mutual fund?"
}


Response

{
  "reply": "An equity mutual fund invests primarily in stocks..."
}

Chat History
GET /history

🎨 Frontend Setup (React)
1️⃣ Install Dependencies
cd frontend
npm install

2️⃣ Start React App
npm run dev


App runs at:

http://localhost:5173

🔗 Frontend → Backend Connection

Example API call:

fetch("http://127.0.0.1:8000/chat", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ message: userMessage }),
});

📚 Chat History

Stored in chat_history.json

Last 50 conversations retained

Automatically saved on every chat

🧠 Model Used

Model: mistral-small

Temperature: 0.2 (accurate, low hallucination)

Context-aware responses

🚧 Future Improvements

🔐 Authentication

📊 User-specific chat history

📁 Upload PDFs from UI

🔎 Advanced document filtering

☁️ Cloud deployment (Docker / Hugging Face / AWS)

⚠️ Disclaimer

This chatbot does not provide financial advice.
Always consult a SEBI-registered financial advisor before making investment decisions.

👨‍💻 Author

Karthik Kallapiran
AI • Full-Stack • RAG Systems
