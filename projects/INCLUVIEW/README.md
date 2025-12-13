# 🗣️ Incluview AI

## Inclusive Language Intelligence Platform

<div align="center">

![Value Adders AI Technologies](https://img.shields.io/badge/Value%20Adders-AI%20Technologies-blue?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.11+-blue?style=for-the-badge)
![React](https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Active-green?style=for-the-badge)

> **"Add value or don't act."** — *The Value Adders Creed*

</div>

---

## Overview

**Incluview AI** is a comprehensive bias detection and remediation platform that helps teams identify, understand, and correct biased language in text-based communications. It supports real-time analysis across multiple bias categories and provides actionable suggestions for more inclusive alternatives.

---

## 🎯 Mission

Make communication more **inclusive, respectful, and accessible** to all humans.

---

## 🌟 Features

| Feature | Description |
|---------|-------------|
| 🔍 **Multi-Category Bias Detection** | 7+ bias categories: gender, age, ableism, race, orientation, socioeconomic, religion |
| ⚡ **Real-time Analysis API** | Fast, accurate detection with configurable sensitivity |
| 🧠 **Adaptive Learning** | User feedback improves detection over time |
| 💡 **Actionable Suggestions** | Each detection includes inclusive alternatives with explanations |
| 🖥️ **Modern Web Interface** | React dashboard for document analysis and reporting |
| 🏢 **Enterprise Ready** | API authentication, Docker deployment, comprehensive logging |

---

## 📊 Bias Categories

### Categories Detected

| Category | Examples |
|----------|----------|
| **Gender** | chairman, guys, manpower, fireman, bossy |
| **Age** | old, elderly, senior moment, boomer, millennial |
| **Ableism** | crazy, lame, insane, wheelchair-bound, tone deaf |
| **Racial/Ethnic** | minority, exotic, urban, third world |
| **Sexual Orientation/Identity** | lifestyle choice, sexual preference, preferred pronouns |
| **Socioeconomic** | the homeless, poor people, underprivileged |
| **Religious** | gypped, extremist (when applied unevenly) |

---

## 💡 How It Works

**Input:**
```
"The chairman asked the guys to finish the report."
```

**Output:**
```json
{
  "detections": [
    {
      "term": "chairman",
      "category": "gender",
      "severity": 0.65,
      "explanation": "Assumes gender in leadership titles.",
      "suggestions": [
        {"replacement": "chairperson", "rationale": "Gender-inclusive alternative."},
        {"replacement": "chair", "rationale": "Neutral title focusing on role."}
      ]
    }
  ]
}
```

---

## 🏗️ Architecture

```
Incluview/
├── backend/         # Flask API, NLP pipeline, model orchestration
├── frontend/        # React SPA for dashboard
├── docs/            # Product strategy, design briefs
└── infrastructure/  # Deployment descriptors
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|------------|
| **Backend** | Python 3.11+, Flask, spaCy |
| **Frontend** | React 18, Material-UI, Vite |
| **NLP** | spaCy, optional transformer models |
| **Container** | Docker, Docker Compose |

---

## 📡 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/v1/health` | Health check |
| POST | `/api/v1/analyze` | Analyze text for bias |
| GET | `/api/v1/categories` | List bias categories |
| POST | `/api/v1/feedback` | Submit adaptive learning feedback |

---

## 💜 The Value Adders Difference

**Traditional Bias Detection:**
- Rigid rule-based systems
- Limited categories
- No learning capability
- Technical output only

**Incluview AI:**
- Adaptive learning from feedback
- 7+ comprehensive categories
- Clear explanations and alternatives
- Human-readable suggestions
- Privacy-first design

---

## 📚 Resources

- [Full Repository](https://github.com/ValueaddersWorld/Incluview)
- [API Documentation](https://docs.valueadders.world/incluview/api)
- [Setup Guide](https://docs.valueadders.world/incluview/setup)

---

<div align="center">

**Incluview AI** — *Making Communication Inclusive*

💜 *Add Value. We Flourish & Prosper.* 💜

</div>
