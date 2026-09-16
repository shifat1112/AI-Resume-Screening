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

📄 Resume Processing

The system supports resume documents in several formats:

i. PDF
ii. DOCX
iii. TXT
iv. JPG
v. JPEG
vi. PNG

Text extraction is performed using format-specific processing tools, while
OCR is used for image-based resumes.

🔍 Information Extraction

The framework extracts structured candidate information including:

Feature	Description
Name	Candidate name
Email	Email address
Phone	Contact number
Skills	Identified technical/professional skills
CGPA	Academic CGPA/GPA when available
Experience	Estimated years of experience
Education	Educational information
Projects	Project-related information
Achievements	Candidate achievements
Experience Details	Professional experience information

spaCy and regular-expression-based processing are used for several extraction
tasks.

🧠 Candidate Matching Approaches
1. Skill & Feature-Based Matching

Candidate features are evaluated using:

Skill matching
Project count
Achievement count
Years of experience

A weighted matching score is calculated from these features.

The current implementation uses:

40% skill matching
20% project score
20% achievement score
20% experience score

2. Semantic Similarity

The project uses the Sentence Transformers model:

all-MiniLM-L6-v2

to generate semantic embeddings for the job description and candidate resume
information.

Cosine similarity is then used to measure semantic relevance between the
candidate information and job description.

3. LLM-Based Evaluation

The project also explores LLM-assisted candidate evaluation using:

--Mistral 7B through Ollama

The LLM receives a job description and resume summary and produces:

--Match score
--Short reasoning for the score

The notebook requests a score on a 0–100 scale together with a textual reason.

📊 Example Candidate Ranking

The feature-based matching stage produces candidate-level values such as:

--Match Score
--Experience Years
--Skills
--Project Score
--Achievement Score

The notebook demonstrates sorting candidates according to their calculated
matching scores.

🛠️ Technologies

Programming:
--Python
--Google Colab

Natural Language Processing:
--spaCy
--Regular Expressions
--Sentence Transformers

Machine Learning:
--Scikit-learn
--TF-IDF
--Cosine Similarity

LLM:
--Mistral 7B
--Ollama

Document Processing:
--PyMuPDF
--pdfplumber
--python-docx
--Tesseract OCR
--Pillow

Data & Visualization:
--Pandas
--NumPy
--Matplotlib
--Seaborn
