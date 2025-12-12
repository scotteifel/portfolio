# SpendingAPI.com

Automated analysis platform for federal government contracts. Fetches, analyzes, and publishes contract data daily.

**Live**: [spendingapi.com](https://spendingapi.com)

## What It Does

- Fetches 500+ federal contracts daily from USAspending.gov public API
- Multi-stage AI analysis using Groq/LLaMA models for cost evaluation
- Generates individual SEO-optimized pages for each contract
- Automated pipeline runs on Railway 

## Technical Highlights

- Handles API pagination (5 pages, 100 contracts per page)
- Rate limiting and error recovery between requests
- Multi-stage data pipeline: fetch → filter → analyze → publish
- AI prompt engineering for consistent contract evaluation
- Cold start optimization for Railway hobby tier

## Architecture

- **Frontend**: Next.js, React, TypeScript, Tailwind CSS
- **Backend**: Next.js API routes
- **AI**: Groq API (LLaMA 3.1)
- **Data Source**: USAspending.gov public API
- **Deployment**: Railway with Docker

Built as a portfolio project to demonstrate full-stack capability, API integration, and AI implementation.

**Tech**: Next.js, TypeScript, React, Docker, Railway, Groq API
