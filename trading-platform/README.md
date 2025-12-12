> **Currently deployed in production, processing live trades across multiple exchanges with 99.9% uptime.**

A production-grade FastAPI trading system currently processing live trades with enterprise-level security and monitoring.

**Horizontally Scaled, Leader-Follower Pattern**

- **3 FastAPI instances** processing webhooks simultaneously
- **Leader (Instance 0)**: Write-enabled, runs scheduled jobs
- **Followers (Instances 2, 5)**: Read-only replicas (commit/flush = no-op)
- **Shared PostgreSQL**: Instance-aware connection pooling (10+20 leader, 5+10 followers)
- **Redis**: Rate limiting (5 req/60s), auto-ban (50 req/hr), whitelist management
- **APScheduler**: 30-min cron jobs for OHLC updates (leader only)

**Key Patterns:**

- Webhook response times optimized for real-time trading requirements
- Event-driven DB audit trail (SQLAlchemy listeners → Telegram alerts)
- Circuit breaker for SSL errors with auto-recovery
- Multi-exchange support (Bitget, Binance, Coinbase)

## 🎯 Business Impact

- **Live Production**: 6+ months uptime, processing real-time trading signals
- **Real Stakes**: Handles real trading decisions and executions
- **Zero Downtime**: Built for 24/7 reliability
- **Multi-User Platform**: Enables non-technical users to deploy strategies independently

## 🏗️ What I Built

Enterprise-grade algorithmic trading platform with:

- FastAPI backend with production security (IP whitelisting, rate limiting, auto-banning)
- PostgreSQL + Redis architecture for performance and caching
- TradingView webhook integration with exchange APIs
- Hedging system for complex risk management
- Railway deployment with GitHub integration

## 🚀 Live in Production

This system has been running in production for 6+ months, handling real trades.

## ✨ Key Features

### Security & Authentication

- IP whitelist verification for endpoints
- API key authentication with environment variables
- HMAC signature generation for exchange requests
- Redis-based rate limiting (5 req/minute default)

### Trading Capabilities

- Automated trade execution via TradingView webhooks
- Automated trade execution on broker OHLC data
- Support for market and limit orders
- Futures trading with margin management
- Intelligent scheduler with cancellation events

### Production Architecture

- Fully async/await implementation
- Dependency injection pattern
- Global state management
- Comprehensive error handling and logging
- Multi-instance coordination support

## 🛠 Tech Stack

**Backend**

- FastAPI (async Python 3.9+)
- SQLAlchemy 2.0 (ORM with event listeners)
- Pydantic (request/response validation)

**Data Layer**

- PostgreSQL (Railway) - Leader-follower writes, instance-aware pooling
- Redis (Upstash) - Distributed rate limiting, auto-bans

**Integrations**

- TradingView webhooks
- Bitget/Binance APIs (REST)
- 3 Telegram bots (dev/user/trading alerts)

**Infrastructure**

- Railway deployment (Nixpacks containerization)
- APScheduler (cron jobs)
- Instance-aware configuration

## 📝 Code Highlights

This repository demonstrates:

- Production-ready async Python
- Distributed system design (leader-follower, fanout patterns)
- Secure API design patterns
- Complex state management
- Professional error handling

## 🔒 Security Notice

Sensitive information and proprietary trading logic have been removed from this public version.

## 👨‍💻 Author

**Scott E.** - Backend Engineer & Equity Partner

- [Upwork Profile] https://www.upwork.com/freelancers/~01528692969b8cd521?mp_source=share
