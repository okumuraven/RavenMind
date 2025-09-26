# 🟣 RavenMind
**"Intelligence that Protects"**

RavenMind is an AI-powered moderation and identity verification system that secures online platforms by detecting harmful content and verifying user identities.

It provides custom APIs for apps like Comrades Market Kenya, PhantomChat, and RavenFleetX, ensuring safety, compliance, and trust without relying on expensive third-party APIs.

---

## 🚀 Features

- **ID Verification** → OCR + Face Matching for user KYC
- **Text Moderation** → Offensive/toxic language detection
- **Image Moderation** → NSFW & harmful content filtering
- **Centralized Logging** → PostgreSQL for audits, compliance, and analysis
- **FastAPI Integration** → Lightweight, fast, and scalable microservice

---

## 🏗️ Architecture Overview

```plaintext
User / App (Comrades Market, PhantomChat, RavenFleetX)
        │
        ▼
   RavenMind API (FastAPI)
        │
 ┌──────┼─────────────┐
 │      │             │
 ▼      ▼             ▼
ID Verification   Text Moderation   Image Moderation
(OCR + Face)      (Rules + ML)      (NSFW Detector)
        │
        ▼
PostgreSQL Database (Logs, Results, Confidence)
        │
        ▼
Integration Layer → Response to Apps (Allow / Block / Flag)
```

---

## 📦 Tech Stack

- **Language:** Python 3.10+
- **Framework:** FastAPI
- **Database:** PostgreSQL (SQLAlchemy ORM)
- **AI Models:**
  - EasyOCR / Tesseract → ID text extraction
  - DeepFace / InsightFace → Face matching
  - Hugging Face Toxicity Classifier → Text moderation
  - NSFW Detector / YOLO → Image moderation

---

## ⚙️ Installation

### 1. Clone Repository

```bash
git clone https://github.com/<your-username>/RavenMind.git
cd RavenMind
```

### 2. Create Virtual Environment

```bash
python -m venv venv
source venv/bin/activate   # Linux / Mac
venv\Scripts\activate      # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Setup PostgreSQL

- Install PostgreSQL and create a database named `ravenmind_db`.
- Update `config.py` with your DB credentials.

### 5. Run FastAPI Server

```bash
uvicorn main:app --reload
```


## 📌 API Endpoints

### 🔹 Verify ID

- **POST** `/verify-id`
- **Input:** ID image + Selfie image
- **Output:** Match/Reject with confidence

### 🔹 Moderate Text

- **POST** `/moderate-text`
- **Input:** Message text
- **Output:** Safe/Blocked with reason

### 🔹 Moderate Image

- **POST** `/moderate-image`
- **Input:** Image
- **Output:** Safe/Blocked with reason

---

## 🗂️ Project Roadmap

- [ ] Setup FastAPI + PostgreSQL
- [ ] Add OCR for ID verification
- [ ] Add face matching module
- [ ] Build text moderation module
- [ ] Add NSFW image detector
- [ ] Deploy to DigitalOcean/AWS
- [ ] Integrate with Comrades Market, PhantomChat, RavenFleetX

---

## 🤝 Contributing

We welcome contributions!

1. Fork the repo
2. Create a branch (feature-xyz)
3. Commit changes
4. Push branch and open a PR

---

## 📜 License

MIT License – Free to use and modify.

---

## 🖤 Credits

Built by Okumu Joseph & Team, with the vision of making African platforms secure, compliant, and community-friendly.

---

**RavenMind**: Intelligence that Protects.
