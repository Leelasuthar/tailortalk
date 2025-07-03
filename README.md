calendar-booking-agent/
├── backend/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── main.py                 # FastAPI app
│   │   ├── models.py               # Pydantic models
│   │   └── agent/
│   │       ├── __init__.py
│   │       ├── calendar_agent.py   # LangGraph agent
│   │       ├── tools.py            # Calendar tools
│   │       └── llm_config.py       # LLM configuration
│   ├── services/
│   │   ├── __init__.py
│   │   ├── calendar_service.py     # Google Calendar integration
│   │   └── auth_service.py         # Service account auth
│   ├── config/
│   │   ├── __init__.py
│   │   └── settings.py             # Environment variables
│   └── requirements.txt
├── frontend/
│   ├── streamlit_app.py           # Streamlit chat interface
│   └── requirements.txt
├── credentials/
│   └── service-account-key.json   # Google service account (gitignored)
├── .env                           # Environment variables
├── .gitignore
├── README.md
└── railway.toml                   # Deployment config









🚀 Setup Instructions
1. Google Calendar Setup

Go to Google Cloud Console
Create a new project or select existing
Enable Google Calendar API
Create Service Account credentials
Download JSON key file to credentials/service-account-key.json
Share your calendar with the service account email

2. Local Development
bash# Clone and setup
git clone <your-repo>
cd calendar-booking-agent

# Backend setup
cd backend
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000

# Frontend setup (new terminal)
cd frontend
pip install -r requirements.txt
streamlit run streamlit_app.py --server.port 8501
3. Deployment (Railway)
bash# Install Railway CLI
npm install -g @railway/cli

# Deploy backend
railway login
railway init
railway up

# Deploy frontend
railway init
railway up
🔧 Key Features

Natural Language Processing: Uses Gemini AI for intent understanding
Tool Calling: LangGraph agent with calendar tools
Real-time Chat: Streamlit interface with chat history
Google Calendar Integration: Service account for seamless booking
Minimal Dependencies: Clean, efficient codebase
Production Ready: Structured for easy deployment

📝 Usage Examples

"Book a meeting tomorrow at 2 PM"
"Is Monday morning available?"
"What times are free on Friday?"
"Schedule a call with client for next week"

The agent will understand these natural language requests and perform the appropriate calendar operations!