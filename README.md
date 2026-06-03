# DisasterAlertAI

A web platform that uses a fine-tuned **BERT classifier** to analyze tweets in real time and determine whether they contain disaster-related information. Built to assist emergency responders and the public during critical events.

## Features

- Real-time tweet analysis using a BERT-based NLP classifier
- Accepts typed tweet text or a tweet URL as input
- Web scraping to extract tweet content from links
- Instant disaster / non-disaster prediction with confidence
- User-friendly web interface with visual result feedback

## Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![BERT](https://img.shields.io/badge/BERT-Hugging%20Face-FFD21E?style=flat&logo=huggingface&logoColor=black)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=css3&logoColor=white)

**Model:** BERT (fine-tuned on the [NLP Getting Started Kaggle dataset](https://www.kaggle.com/competitions/nlp-getting-started))  
**Backend:** FastAPI  
**Frontend:** HTML / CSS / JavaScript

## Setup

```bash
pip install transformers torch fastapi uvicorn requests beautifulsoup4
```

**Run the backend:**
```bash
cd backend
uvicorn main:app --reload
```

**Open the frontend:**  
Open `mywebsite/index.html` in your browser, or serve it with any static server.

## How It Works

1. User enters a tweet or paste a tweet URL into the web interface
2. If a URL is provided, the backend scrapes the tweet text
3. Text is preprocessed and passed to the fine-tuned BERT classifier
4. The model predicts: **Disaster** or **Not a Disaster**
5. The result is returned to the frontend and displayed with visual feedback

## Project Structure

```
DisasterAI/
├── backend/           # FastAPI backend with BERT inference
├── mywebsite/         # Frontend (HTML/CSS/JS)
└── Final_Tweets/      # Training/test tweet datasets
```

## Model Performance

Fine-tuned BERT classifier trained on labeled disaster tweets from the Kaggle NLP competition dataset. BERT's contextual embeddings enable accurate disambiguation of figurative vs. literal disaster language (e.g., *"the crowd was on fire"* vs. *"the building is on fire"*).
