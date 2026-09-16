# 🤖 AI-Powered Resume Screening & Candidate Ranking

An AI-assisted resume screening and candidate ranking framework that combines
resume information extraction, skill matching, experience analysis, semantic
similarity, and Large Language Model (LLM) evaluation.

---

## 📌 Overview

Recruitment teams may need to process large numbers of resumes for a single
job opening. This project explores an automated approach for extracting
structured information from resumes and evaluating candidate-job relevance.

The framework processes resumes from multiple document formats and extracts
information such as skills, education, experience, projects, achievements,
CGPA, email, and phone information.

It then applies different matching approaches, including:

- Rule-based information extraction
- Skill matching
- Experience and project analysis
- TF-IDF-based matching
- Semantic similarity using Sentence Transformers
- LLM-based resume evaluation using Mistral 7B through Ollama

---

## 🎯 Objectives

- Automate the extraction of relevant information from resumes.
- Identify candidate skills and professional experience.
- Analyze projects and achievements.
- Calculate candidate-job matching scores.
- Compare lexical and semantic matching approaches.
- Explore LLM-assisted candidate evaluation.
- Produce an interpretable candidate ranking framework.

---

## 🏗️ System Workflow

```text
Resume Documents
       │
       ▼
┌──────────────────────┐
│ Resume Text          │
│ Extraction           │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Information          │
│ Extraction           │
│                      │
│ • Skills             │
│ • Education          │
│ • Experience         │
│ • Projects           │
│ • Achievements       │
│ • CGPA               │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│ Candidate            │
│ Feature Processing   │
└──────────┬───────────┘
           │
     ┌─────┼──────────────┐
     ▼     ▼              ▼
   TF-IDF  Semantic       LLM
           Similarity     Evaluation
     │     │              │
     └─────┼──────────────┘
           ▼
┌──────────────────────┐
│ Candidate Matching    │
│ & Ranking             │
└──────────────────────┘
