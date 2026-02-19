# 🧠 NL2SQL Intelligent Assistant

### AI-Powered Natural Language → PostgreSQL Querying System

An intelligent Natural Language to SQL assistant that allows users to interact with a PostgreSQL database using plain English questions.

This project demonstrates how **Large Language Models**, **Retrieval Augmented Generation (RAG)**, and **Dynamic Few-Shot Learning** significantly improve SQL generation accuracy.

Built as a **Generative AI Portfolio Project** focused on real-world AI system engineering.

---

## 🚀 Live Concept

Example:

```
User:
How many customers are in the United States?
```

↓

AI understands database values and generates:

```sql
SELECT COUNT(*) 
FROM "Customer"
WHERE "Country" = 'USA';
```

↓

Returns result + explanation in natural language.

---

# ⭐ Project Versions

This repository includes **two different architectures** to compare NL2SQL approaches.

---

## 1️⃣ Basic NL2SQL Assistant — Prompt Engineering

File:

```
app_basic.py
```

Features:

* Schema-aware SQL generation.
* PostgreSQL strict formatting rules.
* Natural language explanations.
* SELECT-only safety enforcement.

Best for:

* Understanding Prompt Engineering.
* Lightweight deployments.

Architecture:

```
User Question
     ↓
Prompt Engineering
     ↓
Gemini LLM
     ↓
SQL Query
     ↓
Database Execution
     ↓
Natural Language Answer
```

---

## 2️⃣ Dynamic Few-Shot + RAG Assistant ⭐ (Recommended)

File:

```
app_dynamic.py
```

Advanced system using:

* Semantic similarity search.
* Vector Database retrieval.
* Dynamic example selection.

Problem solved:

```
Database Value → USA
User Question → United States
```

Basic LLM fails.

Dynamic Few Shot retrieves similar examples automatically.

Architecture:

```
User Question
      ↓
Embedding Model
(sentence-transformers)

      ↓
Chroma Vector Store Search

      ↓
Top Similar Examples Selected

      ↓
Few Shot Prompt Construction

      ↓
Gemini LLM

      ↓
Generated SQL

      ↓
Execute Query

      ↓
Natural Language Answer
```

Benefits:

✅ Better synonym understanding.
✅ Reduced hallucinations.
✅ Higher SQL accuracy.

---

# 🧠 Technologies Used

* Python
* LangChain
* Streamlit
* PostgreSQL
* Google Gemini (gemini-2.5-flash)
* HuggingFace Embeddings
* Chroma Vector Database
* Retrieval Augmented Generation (RAG)

---

# 📂 Repository Structure

```
nl2sql-intelligent-assistant

│
├── app_basic.py
├── app_dynamic.py
│
├── fewshots.json
├── deploy.py
│
├── requirements.txt
└── README.md
```

---

# ⚙️ Installation

Clone repository:

```
git clone https://github.com/ebraamnabil01-code/nl2sql-intelligent-assistant.git
```

Move into folder:

```
cd nl2sql-intelligent-assistant
```

Create virtual environment:

Windows:

```
python -m venv venv
venv\Scripts\activate
```

Install dependencies:

```
pip install -r requirements.txt
```

---

# 🔐 Environment Variables

Create `.env` file:

```
GOOGLE_API_KEY=your_google_api_key
DB_URL=postgresql://username:password@localhost/database
```

---

# 🗄️ Database Setup

Dataset:

```
PostgreSQL Chinook Dataset
```

Upload CSV files:

```
python deploy.py
```

This script:

* Creates tables automatically.
* Uploads CSV datasets.
* Verifies successful insertion.

---

# ▶️ Running The Application

---

## Basic Version

```
streamlit run app_basic.py
```

---

## Dynamic Few Shot + RAG Version ⭐

```
streamlit run app_dynamic.py
```

---

# 🔒 Safety Controls

The system enforces:

* SELECT queries only.
* No INSERT / UPDATE / DELETE.
* Schema restricted SQL generation.
* Automatic LIMIT protection.
* PostgreSQL syntax enforcement.

---

# 📊 Example Questions

```
List all customers
Total invoices
Top selling tracks
Revenue by country
How many customers live in Canada?
```

---

# 📈 Architecture Comparison

| Version     | Accuracy | Flexibility | Complexity |
| ----------- | -------- | ----------- | ---------- |
| Basic       | Medium   | Low         | Simple     |
| Dynamic RAG | High     | High        | Medium     |

---

# 🎯 Learning Goals

This project explores:

* Natural Language Interfaces to Databases.
* Retrieval Augmented Generation.
* Dynamic Few Shot Learning.
* Prompt Engineering.
* LLM Application Design.

---

# 👨‍💻 Author

Author: **Ebraam Nabil**

GitHub:

https://github.com/ebraamnabil01-code

---

# ⭐ Future Improvements

* Query visualization charts.
* Multi database support.
* Query explanation mode.
* Caching frequent queries.

---

⭐ If you find this project useful, consider starring the repository.


