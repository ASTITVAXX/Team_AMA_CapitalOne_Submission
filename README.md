# 🌾 Agricultural Advisor Bot

> *⚠ Important*: Add your Groq API key to run this application.    Use this Free GROQ_API_KEY - "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", just put this in .env file while running.

A comprehensive AI-powered multilingual agricultural advisor that provides personalized farming advice, weather insights, market prices, and government policy information in *Hindi* and *English*. Built with advanced NLP, weather services, and LLM integration.


## 🌟 Overview

The Agricultural Advisor Bot is an intelligent system designed to assist Indian farmers with comprehensive agricultural information. It combines multiple AI technologies to provide accurate, timely, and actionable advice.

### Key Capabilities:
- *Multilingual Support*: Hindi and English with automatic language detection
- *Weather Analysis*: 7-day forecasts with agricultural insights
- *Price Intelligence*: Real-time mandi prices across India
- *Policy Guidance*: Government scheme information and eligibility
- *Smart Classification*: 6 intent categories with AI-powered understanding


## ⚠ Installation Time Notice
*Important: The initial setup may take **5-10 minutes* due to large AI models and libraries being downloaded. This is normal for the first run.

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- Git
- Internet connection for model downloads
- At least 2GB free disk space

### System Requirements
- *RAM*: Minimum 4GB, Recommended 8GB+
- *Storage*: 2GB+ free space
- *OS*: Windows 10+, macOS 10.14+, Ubuntu 18.04+

## 📋 Setup Instructions

### Method 1: One-Click Setup (Recommended)

bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/agricultural-advisor-bot.git
cd agricultural-advisor-bot

# Run complete setup (takes 5-10 minutes)
python setup_and_run.py

# Or use platform-specific scripts:
# Windows: run_setup.bat
# Linux/Mac: ./run_setup.sh


### Method 2: Manual Setup

bash
# 1. Clone repository
git clone https://github.com/YOUR_USERNAME/agricultural-advisor-bot.git
cd agricultural-advisor-bot

# 2. Install dependencies (takes 5-10 minutes)
pip install -r requirements.txt

# 3. Initialize database and data
python init_mandi_soil.py

# 4. Create vector database for policies
python improved_policy_chatbot.py

# 5. Verify setup
python agricultural_advisor_bot.py --help


### Method 3: Development Setup

bash
# 1. Create virtual environment
python -m venv venv

# 2. Activate virtual environment
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Install development dependencies
pip install -r requirements_streamlit.txt

# 5. Initialize data
python init_mandi_soil.py
python improved_policy_chatbot.py


## 🛠 Usage

### Command Line Interface

bash
# Interactive mode
python agricultural_advisor_bot.py --interactive

# Single query
python agricultural_advisor_bot.py --query "गेहूं का भाव क्या है" --city "Kanpur"

# Weather query
python agricultural_advisor_bot.py --query "मौसम कैसा है" --city "Mumbai"

# Policy query
python agricultural_advisor_bot.py --query "PM Kisan scheme details"

# Help
python agricultural_advisor_bot.py --help


### Web Interface

bash
# Install Streamlit dependencies
pip install -r requirements_streamlit.txt

# Run web interface
streamlit run streamlit_app.py

# Access at: http://localhost:8501


### API Usage

python
from agricultural_advisor_bot import AgriculturalAdvisorBot

# Initialize bot
bot = AgriculturalAdvisorBot()

# Set user preferences
bot.set_user_city("Kanpur")
bot.set_user_language("Hindi")

# Process query
response = bot.process_query("गेहूं का भाव क्या है")
print(response)



## 🌟 Features

### 🌍 *Multilingual Support*
- *Hindi & English*: Automatic language detection and response generation
- *Hindi Keywords*: गेहूं, चावल, मौसम, भाव, मंडी, etc.
- *Code-mixed Text*: Handles mixed Hindi-English queries seamlessly

### 🎯 *Smart Query Classification*
- *6 Intent Categories*: Weather, Policy, Price, Technical, Agriculture, General
- *Advanced NLP*: Transformer-based classification with fallback mechanisms
- *Context Awareness*: Understands agricultural terminology in both languages

### 💰 *Intelligent Price Queries*
- *LLM-based SQL Generation*: Natural language to SQL conversion
- *Complex Queries*: Compare prices, trends, best mandis, latest rates
- *Real-time Data*: 35,522+ price records from mandis across India
- *Fallback Mechanisms*: Robust error handling and alternative data sources

### 🌤 *Weather-Based Farming Advice*
- *Comprehensive Weather Data*: Historical + 7-day forecast
- *Agricultural Insights*: Soil moisture, crop health, irrigation needs
- *Location Intelligence*: Automatic geocoding and timezone detection
- *AI-Generated Advice*: Personalized recommendations based on weather

### 📋 *Government Policy Support*
- *12 Policy Documents*: PM Kisan, PMKSY, Soil Health Card, Crop Insurance
- *Vector Database*: 973 sections with semantic search
- *Groq Integration*: Advanced LLM for policy explanations






## 📊 Data Sources

### Price Data 💰
- *Source*: mandi_prices.csv (35,522 records)
- *Coverage*: Multiple states, districts, mandis across India
- *Fields*: Commodity, Variety, Min/Max/Modal Price, Arrival Date
- *Database*: SQLite with optimized queries

### Weather Service 🌤
- *API*: Open-Meteo (free, no API key required)
- *Data*: Historical (20 days) + Forecast (7 days)
- *Insights*: Soil moisture, crop health, irrigation needs
- *Coverage*: Global with automatic geocoding

### Policy Documents 📋
- *Documents*: 12 PDF files (PM Kisan, PMKSY, etc.)
- *Processing*: Vector embeddings (973 sections)
- *Search*: Semantic similarity with Groq LLM
- *Database*: FAISS vector database

### Soil Health Data 🌱
- *Source*: soil_health.csv (5 districts)
- *Parameters*: pH, Organic Carbon, N-P-K levels
- *Integration*: Crop recommendations based on soil data

## 🛠 Technical Stack

### Core Technologies
- *Python 3.8+*: Main programming language
- *SQLite*: Local database for price and soil data
- *FAISS*: Vector database for policy documents
- *Groq API*: LLM for AI responses (Llama3-8b-8192)

### NLP & ML
- *Transformers*: Hugging Face for language models
- *spaCy*: Named Entity Recognition
- *Sentence Transformers*: Semantic similarity
- *NLTK*: Text processing utilities

### Weather & APIs
- *Open-Meteo*: Weather data API
- *Geocoding*: Location services
- *Requests*: HTTP client for API calls

### Data Processing
- *Pandas*: Data manipulation
- *NumPy*: Numerical computations
- *SQLAlchemy*: Database ORM (optional)

### Web Interface
- *Streamlit*: Web application framework
- *Plotly*: Interactive visualizations
- *Bootstrap*: UI components



## 🔌 API Integration

### Environment Variables



# Optional: Weather API key (Open-Meteo is free)
export WEATHER_API_KEY=your_weather_api_key_here

# Optional: Database configuration
export DATABASE_URL=sqlite:///agri_data.db


### Configuration File

Create config.py for custom settings:

python
# OPTIONAL config.py
GROQ_API_KEY = "your_api_key_here"
WEATHER_API_KEY = "your_weather_api_key_here"
DEFAULT_LANGUAGE = "Hindi"
DEFAULT_CITY = "Kanpur"
LOG_LEVEL = "INFO"


## 🔧 Troubleshooting

### Common Issues

#### 1. Installation Timeout
bash
# Increase pip timeout
pip install --timeout 1000 -r requirements.txt

# Use alternative package index
pip install -i https://pypi.org/simple/ -r requirements.txt


#### 2. Memory Issues
bash
# Reduce model size in config
export TRANSFORMERS_CACHE="/tmp/transformers_cache"
export HF_HOME="/tmp/huggingface"


#### 3. Database Errors
bash
# Reinitialize database
python init_mandi_soil.py

# Check database integrity
python -c "import sqlite3; conn = sqlite3.connect('agri_data.db'); print('Database OK')"


#### 4. Vector Database Issues
bash
# Recreate vector database
python improved_policy_chatbot.py

# Check vector database
python -c "import pickle; data = pickle.load(open('improved_vector_db/documents.pkl', 'rb')); print(f'Documents: {len(data)}')"


### Performance Optimization

#### 1. Reduce Model Loading Time
python
# In agricultural_advisor_bot.py
import os
os.environ['TRANSFORMERS_CACHE'] = '/path/to/cache'
os.environ['HF_HOME'] = '/path/to/huggingface'


#### 2. Enable Caching
python
# Enable Streamlit caching
@st.cache_data
def load_data():
    return pd.read_csv('mandi_prices.csv')


#### 3. Optimize Database Queries
python
# Use indexes for faster queries
CREATE INDEX idx_commodity ON mandi_prices(Commodity);
CREATE INDEX idx_date ON mandi_prices(Arrival_Date);



## 🌟 Key Innovations

### 1. Multilingual LLM Integration
- Automatic language detection and response generation
- Hindi-specific prompts and system messages
- Code-mixed text handling

### 2. LLM-based SQL Generation
- Natural language to SQL conversion
- Complex query support (comparisons, trends, best mandis)
- Robust fallback mechanisms

### 3. Comprehensive Weather Analysis
- Agricultural insights from weather data
- Soil moisture and irrigation recommendations
- Crop health assessment

### 4. Policy Document Intelligence
- Vector-based semantic search
- LLM-powered policy explanations
- Multi-document knowledge base

## 🤝 Contributing

### Development Setup
bash
# Fork the repository
git clone https://github.com/YOUR_USERNAME/agricultural-advisor-bot.git
cd agricultural-advisor-bot

# Create feature branch
git checkout -b feature/amazing-feature

# Make changes and test
python agricultural_advisor_bot.py --test

# Commit changes
git commit -m 'Add amazing feature'

# Push to branch
git push origin feature/amazing-feature

# Create Pull Request


### Code Style
- Follow PEP 8 guidelines
- Add type hints where possible
- Include docstrings for functions
- Write unit tests for new features

### Testing
bash
# Run tests
python -m pytest tests/

# Run linting
flake8 agricultural_advisor_bot.py

# Run type checking
mypy agricultural_advisor_bot.py


## 📝 License

This project is licensed under IIT Kanpur

## 🙏 Acknowledgments

- *Groq*: For LLM API services
- *Open-Meteo*: For weather data
- *Hugging Face*: For transformer models
- *Agricultural Experts*: For domain knowledge validation
- *Indian Farmers*: For inspiration and feedback

### Useful Commands
bash
# Check system status
python agricultural_advisor_bot.py --status

# View logs
tail -f logs/app.log

# Test all components
python agricultural_advisor_bot.py --test-all

# Get help
python agricultural_advisor_bot.py --help


*🌾 Empowering Indian Farmers with AI-Powered Agricultural Intelligence* 🌾

Built with ❤ for the farming community
