
# Social Sentiment Flask ⚡  
### Real-time Social Media Sentiment Analysis with Hugging Face Transformers & Interactive Word Clouds

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-3.0%2B-lightgrey)](https://flask.palletsprojects.com/)
[![Docker](https://img.shields.io/badge/Docker-Ready-blue)](https://www.docker.com/)

A beautiful, fast, and lightweight web application that analyzes sentiment from social media text (Twitter/X, Reddit, comments, etc.) using state-of-the-art **Hugging Face Transformers** and visualizes results with interactive **word clouds**.

Live Demo: https://social-sentiment-flask.yourdomain.com *(coming soon)*

## ✨ Features

- Real-time sentiment analysis (Positive / Negative / Neutral)
- Confidence scores & emotion breakdown
- Stunning interactive word clouds (positive vs negative words)
- Supports multiple transformer models (DistilBERT, RoBERTa, twitter-xlm-roberta, etc.)
- Clean, responsive UI built with Bootstrap + Chart.js
- REST API endpoint for integration
- Fully Dockerized – run with one command
## 🚀 Quick Start (Docker – Recommended)

```bash
git clone https://github.com/ML-nerd-dev/social-sentiment-flask.git
cd social-sentiment-flask

# Build and run with Docker
docker build -t social-sentiment-flask .
docker run -p 5000:5000 social-sentiment-flask
Open http://localhost:5000
🛠 Local Development Setup
# Clone the repo
git clone https://github.com/ML-nerd-dev/social-sentiment-flask.git
cd social-sentiment-flask

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run the app
python app.py
export SENTIMENT_MODEL="cardiffnlp/twitter-roberta-base-sentiment-latest"
curl -X POST http://localhost:5000/analyze \
  -H "Content-Type: application/json" \
  -d '{"text": "I love this product! Amazing quality and fast delivery ❤️"}'
{
  "sentiment": "POSITIVE",
  "confidence": 0.98,
  "positive_words": ["love", "amazing", "quality", "fast", "delivery"],
  "negative_words": []
}
# Already included in repo
docker build -t social-sentiment-flask .
docker run -d -p 5000:5000 --name sentiment-app social-sentiment-flask
