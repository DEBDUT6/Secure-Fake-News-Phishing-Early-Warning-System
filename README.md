# Secure Fake News & Phishing Early Warning System

## Problem Statement
Misinformation and phishing links spread through communities faster than people can verify them. Rural, elderly, and first-time internet users are especially vulnerable, and by the time a scam or rumor is debunked, it has usually already reached most of the group. This project provides a community-scoped early warning system that detects, verifies, and alerts people before the damage is done.

## Target User
- Local communities and neighborhood groups
- Schools and colleges
- Panchayats and local government bodies
- Cyber cells and NGOs

## Core Features
- Forward suspicious links or messages to a bot for instant checking
- Phishing URL scanning (blacklists, domain age, lookalike domains)
- Fact-check cross-referencing for misinformation claims
- Community-wide alert broadcasting (Telegram/SMS/WhatsApp)
- Admin dashboard for moderators to review borderline cases
- Education layer explaining why content was flagged

## Concepts Used
- NLP-based text classification
- Heuristic-based URL/threat analysis
- REST API integration (Safe Browsing, VirusTotal, Fact Check API)
- Event-driven bot handling
- Exception handling and input validation

## Architecture Description
The system follows a pipeline structure: a bot ingests forwarded content, a scanner/classifier scores it, high-confidence results are auto-flagged while borderline cases go to a human moderator, and verified alerts are broadcast to the community. Threat-intel and fact-check data are pulled from external APIs, and results are logged for dashboard reporting and model feedback.

## Tech Stack
- Backend: Python (FastAPI)
- Bot: python-telegram-bot
- Threat Intel: Google Safe Browsing, VirusTotal, WHOIS
- Fact-Checking: Google Fact Check Tools API
- Database: PostgreSQL / MongoDB

## How to Run
1. Install dependencies:
   pip install fastapi uvicorn python-telegram-bot python-whois requests
2. Add your API keys to a .env file:
   GOOGLE_SAFE_BROWSING_KEY=
   VIRUSTOTAL_API_KEY=
   GOOGLE_FACT_CHECK_KEY=
   TELEGRAM_BOT_TOKEN=
3. Run the backend:
   uvicorn backend.main:app --reload
4. Run the bot:
   python bot/bot.py


