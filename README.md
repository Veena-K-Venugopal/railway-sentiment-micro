# 💭 Railway Sentiment Micro Project

*A tiny end-to-end ML &rarr; API &rarr; Cloud &rarr; Logging &rarr; UI workflow*

This project will go through these steps:

1. Training a small sentiment classifier (scikit-learn + TF-IDF)
2. Packaging it as a prediction endpoint using FastAPI
3. Deploying the API to Railway
4. Logging predictions to a Railway Postgres database
5. Displaying predictions + logs in a simple one-page frontend

## 🎯Goals

Learn to:
- train a text classification model from scratch
- save & load ML artifacts in production
- build FastAPI backend with ```/predict```
- connect a Railway-managed Postgres database
- log predictions and retrieve them via API
- build a basic HTML + JS frontend talking to your API
- deploy the whole thing as a single Railway service

## ⏩ Project Phases

1. Train the Model (Local Only)
2. Build the API
3. Add Simple Frontend
4. Deploy to Railway
