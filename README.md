# 🌾 Agricultural Advisor Bot

A multilingual AI-powered agricultural advisor providing farming advice, weather insights, market prices, and government policy information in Hindi and English.

## ⚠ Installation Time Notice

*Important*: The initial setup may take 5-10 minutes due to large AI models and libraries being downloaded. This is normal for the first run.

## 🚀 Quick Start

### One-Click Setup (Recommended)
bash
# Clone and setup
git clone "your repo-url"
cd Capital1

# Run complete setup (takes 5-10 minutes)
python setup_and_run.py

# Or use platform scripts:
# Windows: run_setup.bat
# Linux/Mac: ./run_setup.sh


### Manual Setup
bash
# Install dependencies (takes 5-10 minutes)
pip install -r requirements.txt

# Initialize database and data
python init_mandi_soil.py

# Run the bot
python agricultural_advisor_bot.py --interactive


## 🌟 Features

- *Multilingual*: Hindi & English support
- *Weather Analysis*: 7-day forecasts with farming insights
- *Price Queries*: Real-time mandi prices across India
- *Policy Information*: Government schemes and guidelines
- *Smart Classification*: 6 intent categories with AI

## 🔄 Query Workflow

### 1. *Input Processing*

User Query → Language Detection → Intent Classification → Entity Extraction


### 2. *Intent Classification*
- *Weather*: Location-based weather analysis and farming advice
- *Price*: Mandi price queries with SQL generation
- *Policy*: Government scheme information search
- *Technical*: Agricultural technical advice
- *Agriculture*: General farming queries
- *General*: Other queries

### 3. *Specialized Processing*
- *Weather Queries*: Open-Meteo API → Agricultural insights
- *Price Queries*: LLM SQL generation → Database search
- *Policy Queries*: Vector search → LLM explanation

### 4. *Response Generation*
- Language-specific formatting (Hindi/English)
- Concise, actionable advice
- Source attribution and confidence scores

## 📊 Data Sources

- *Price Data*: 35,522 mandi records
- *Weather*: Open-Meteo API
- *Policies*: 12 government documents
- *Soil Health*: 5 districts data

## 🗄 Vector Database Setup

### Create Improved Vector Database
bash
# Process policy documents and create vector embeddings
python improved_policy_chatbot.py

# This will:
# - Process all PDFs in the pdfs/ folder
# - Create embeddings for 973 policy sections
# - Store in improved_vector_db/ directory
# - Generate metadata for semantic search


### Vector Database Structure

improved_vector_db/
├── doc_embeddings.npy      # Document-level embeddings
├── section_embeddings.npy  # Section-level embeddings
├── documents.pkl          # Processed document data
└── metadata.json          # Search metadata


## 🛠 Usage Examples

bash
# Interactive mode
python agricultural_advisor_bot.py --interactive

# Single query
python agricultural_advisor_bot.py --query "गेहूं का भाव क्या है" --city "Kanpur"

# Weather query
python agricultural_advisor_bot.py --query "मौसम कैसा है" --city "Mumbai"

# Policy query
python agricultural_advisor_bot.py --query "PM Kisan scheme details"


## 🌐 Web Interface

bash
# Install Streamlit dependencies
pip install -r requirements_streamlit.txt

# Run web interface
streamlit run streamlit_app.py


## 📁 Key Files

- agricultural_advisor_bot.py - Main bot application
- streamlit_app.py - Web interface
- setup_and_run.py - Complete setup script
- weather_service.py - Weather data service
- improved_policy_chatbot.py - Vector database creation
- agri_data.db - SQLite database
- mandi_prices.csv - Price data
- soil_health.csv - Soil data

## 🔧 Configuration

bash
# Optional: Set Groq API key for enhanced responses
export GROQ_API_KEY=your_api_key_here


## 📞 Support

- Check help: python agricultural_advisor_bot.py --help
- Create issues on GitHub
- Contact development team

---

*🌾 Empowering Indian Farmers with AI-Powered Agricultural Intelligence*
