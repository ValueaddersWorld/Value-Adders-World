# 💰 Akuoma

## AI-Powered Microfinance for Financial Inclusion

<div align="center">

![Value Adders AI Technologies](https://img.shields.io/badge/Value%20Adders-AI%20Technologies-blue?style=for-the-badge)
![Mission](https://img.shields.io/badge/Mission-Financial%20Inclusion-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Development-yellow?style=for-the-badge)

> **"Add value or don't act."** — *The Value Adders Creed*

</div>

---

## Overview

**Akuoma** empowers underserved communities with accessible microloans through AI-powered trust modeling. Our platform combines intelligent risk assessment, transparent lending practices, and a mobile-first experience to make financial inclusion a reality.

---

## 🎯 Mission

Break the cycle of poverty through intelligent lending that **serves** the underbanked, not **exploits** them.

---

## ✨ Features

### For Borrowers

| Feature | Description |
|---------|-------------|
| 📱 **Mobile-First** | React Native app optimized for low-bandwidth |
| 🤖 **AI Financial Coach (HLS)** | Personalized guidance powered by GPT-4 |
| 📊 **Value Score™** | Dynamic trust score that improves with positive behavior |
| ⚡ **Fast Approvals** | 30-second AI-powered loan decisions |
| 💳 **Flexible Terms** | €100-€5,000 loans with 7-90 day terms |

### For the Platform

| Feature | Description |
|---------|-------------|
| 🔒 **Privacy-First** | End-to-end encryption with secure KYC |
| 🧠 **Intelligent Risk Engine** | Multi-factor AI assessment using LangChain |
| 📈 **Real-Time Analytics** | Comprehensive dashboards |
| 🌐 **Scalable Architecture** | Microservices with Docker |

---

## 📊 Value Score™ System

The Value Score™ is a proprietary trust metric that reflects a borrower's financial behavior — and rewards growth.

### Tiers

| Tier | Score | Max Loan | Base Rate |
|------|-------|----------|-----------|
| 🌱 Building | 300-450 | €500 | 16%+ |
| 📈 Developing | 451-600 | €1,500 | 12-15% |
| ⭐ Established | 601-750 | €3,000 | 8-11% |
| 👑 Premium | 751-850 | €5,000 | 5-7% |

### How to Improve Your Score

| Event | Points |
|-------|--------|
| ✅ KYC Verified | +25 |
| ✅ First Loan Repaid | +30 |
| ✅ On-Time Payment | +20 |
| ✅ Early Payment | +25 |
| ✅ Referral Signs Up | +10 |
| ✅ Referral First Loan | +25 |
| ⚠️ Late Payment (7 days) | -10 |
| ⚠️ Late Payment (30 days) | -25 |
| ❌ Default | -100 |

---

## 🏗️ Architecture

```
akuoma/
├── backend/              # Node.js + Express REST API
│   ├── src/
│   │   ├── controllers/  # Request handlers
│   │   ├── middlewares/  # Auth, error handling
│   │   ├── routes/       # API route definitions
│   │   └── services/     # Business logic
│   └── prisma/           # Database schema
│
├── ai-service/           # LangChain + OpenAI microservice
│   └── src/
│       ├── routes/       # AI API routes
│       └── services/     # Risk & chat services
│
├── frontend/             # React Native (Expo) mobile app
│   └── src/
│       ├── screens/      # App screens
│       ├── components/   # UI components
│       └── services/     # API client
│
└── docker-compose.yml    # Full stack orchestration
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Backend** | Node.js 20, Express 4.21, TypeScript 5.7 |
| **Database** | PostgreSQL 16, Prisma 5.22 ORM |
| **AI** | LangChain 0.3, OpenAI GPT-4 |
| **Mobile** | React Native 0.73, Expo 50 |
| **Cache** | Redis 7 |
| **Container** | Docker, Docker Compose |

---

## 💜 The Value Adders Difference

**Traditional Microfinance:**
- High interest rates that trap borrowers
- Opaque terms and hidden fees
- Punitive late payment policies
- One-size-fits-all approach

**Akuoma:**
- Rates that decrease as you grow
- Transparent, clear terms
- Support-first approach to struggles
- AI-personalized experience
- Financial education built-in

---

## 🔐 Privacy & Security

- **End-to-end encryption** for all personal data
- **Secure KYC verification** with minimal data collection
- **PathLog integration** for threat detection
- **GDPR/POPIA compliant** data handling

---

## 📚 Resources

- [Full Repository](https://github.com/ValueaddersWorld/akuoma)
- [API Documentation](https://docs.valueadders.world/akuoma/api)
- [Mobile App Guide](https://docs.valueadders.world/akuoma/app)

---

<div align="center">

**Akuoma** — *Financial Inclusion Through AI*

💜 *Add Value. We Flourish & Prosper.* 💜

</div>
