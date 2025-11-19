🏥🤖 Medical LLM Chatbot

A secure, intelligent, and advanced Medical Chatbot powered by Large Language Models (LLMs) using Python.
This chatbot provides general medical information, symptom guidance, and health literacy support, with built-in safety filters, disclaimers, and LLM-guardrails.

⚠️ This system is NOT a medical diagnostic tool. It does not replace licensed healthcare professionals.

🚀 Key Features
🧠 AI & Medical Intelligence

LLM-powered medical Q&A

Symptom explanation & general advice

Medical terminology simplification

Context-aware conversation flow

🛡️ Safety & Reliability

Multi-layer medical safety guardrails

Automatic clinical disclaimer replies

Restricted outputs for unsafe topics

Bias & hallucination reduction techniques

⚙️ Developer Features

FastAPI backend

Modular Python architecture

Custom system & safety prompts

Pluggable LLM providers (OpenAI / Llama / HuggingFace)

Environment-driven configuration

Easy Docker deployment

🏗️ System Architecture
                    ┌─────────────────────────────┐
                    │        User Interface        │
                    │ (Web / Mobile / Postman)     │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │          FastAPI API         │
                    ├──────────────────────────────┤
                    │  /chat endpoint              │
                    │  Safety layer middleware     │
                    │  Response formatter          │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │     LLM Engine (Python)      │
                    │  - OpenAI GPT                │
                    │  - Llama / HF Transformers   │
                    └──────────────┬──────────────┘
                                   │
                                   ▼
                    ┌─────────────────────────────┐
                    │  Medical Safety Prompts      │
                    │  Symptom Rules Engine        │
                    │  Disclaimer Generator        │
                    └─────────────────────────────┘

📦 Installation & Setup
1️⃣ Clone the repository
git clone https://github.com/yourusername/medical-llm-chatbot.git
cd medical-llm-chatbot

2️⃣ Create a virtual environment
python -m venv venv
source venv/bin/activate  # Linux / Mac
venv\Scripts\activate     # Windows

3️⃣ Install dependencies
pip install -r requirements.txt

4️⃣ Add your API key

Create a .env file:

OPENAI_API_KEY=your_key_here
MODEL_NAME=gpt-4o

▶️ Running the Chatbot (FastAPI)
uvicorn app:app --reload


The API will be live at:

http://localhost:8000/docs


Swagger UI automatically generated.

🧩 API Documentation
POST /chat

Send a user question and receive a safe medical response.

Request Example
{
  "query": "I have a headache and light fever. What should I do?"
}

Response Example
{
  "reply": "A mild fever with a headache can be caused by dehydration, viral infection, or stress. Drink plenty of water, rest well, and consider paracetamol if needed. If symptoms worsen or last more than 48 hours, please consult a doctor."
}

🔐 Medical Safety Layer

The medical chatbot uses:

✅ System Safety Prompts

Never diagnose diseases

Never prescribe medication or dosage

Always add a safety disclaimer

✅ Rule-based Filters

Detect emergency symptoms

Provide correct escalation steps

Avoid harmful advice

✅ LLM Guardrails

No hallucinated medicines

No fabricated facts

Encourages professional consultation

📁 Project Structure
📦 medical-llm-chatbot
 ├── app.py                 # FastAPI main application
 ├── services/
 │     ├── llm_engine.py    # LLM communication layer
 │     ├── safety.py        # Safety + medical rules
 │     └── prompts.py       # System & safety prompts
 ├── models/
 │     └── request_model.py # Request/response schemas
 ├── .env                   # API keys
 ├── requirements.txt
 ├── README.md
 └── Dockerfile

🧰 Customization Options

You can easily extend:

🔹 Model Selection
MODEL_NAME = "gpt-4o"  # or llama3, mistral, medllama

🔹 Temperature
temperature=0.2

🔹 Medical Persona
SYSTEM_PROMPT = """
You are a medical information assistant.
Provide general, safe, non-diagnostic guidance.
"""

Google Cloud Run

🤝 Contributing

Contributions are welcome!
You can help with:

Medical dataset improvement

UI interface

Better safety guardrails

Additional provider integrations
