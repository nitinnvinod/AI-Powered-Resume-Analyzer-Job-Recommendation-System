# AI-Powered-Resume-Analyzer-Job-Recommendation-System
AI-Powered Resume Analyzer &amp; Job Recommendation System that extracts skills using NLP, evaluates resumes, and recommends matching job roles using ML-based similarity scoring. Includes parsing, scoring, recommendations, and clean modular architecture.

AI-Powered Resume Analyzer & Job Recommendation System

An intelligent system designed to analyze resumes, extract relevant skills and keywords, evaluate resume quality, and recommend suitable job roles using Machine Learning and Natural Language Processing techniques.

This project aims to assist job seekers in improving their resumes and identifying relevant job opportunities based on qualifications, skills, and experience.

📌 Table of Contents

Overview

Features

System Architecture

Tech Stack

Folder Structure

Installation & Setup

How It Works

Sample Code Snippets

Execution

Testing Instructions

Future Enhancements

License

📖 Overview

This system processes resumes in PDF/text format, extracts meaningful information using NLP pipelines, evaluates content using scoring algorithms, and recommends suitable job roles based on similarity with stored job descriptions.

It integrates resume analysis, feedback generation, and job matching into an automated workflow.

🚀 Features
Feature	Description
Resume Parsing	Extracts skills, experience, education & keywords
NLP Skill Extraction	Uses ML models and token classification
Job Role Recommendation	Suggests job roles based on semantic similarity
Resume Quality Score	Generates score using keyword density & industry benchmarks
Feedback Suggestions	Highlights missing skills and improvements
Modular Architecture	Clean separation of models, UI, and logic
📐 System Architecture
User Input → Resume Parser → NLP Engine → Matching Engine → Job Recommendation
                                      ↓
                                 Resume Scoring

🧰 Tech Stack
Layer	Technology
Programming Language	Python
NLP Frameworks	spaCy, NLTK
Machine Learning	Scikit-Learn, TF-IDF, Sent2Vec
Backend	Flask / Streamlit
Storage	SQLite / CSV / JSON
Other Tools	NumPy, Pandas, PyPDF2, Git
📁 Folder Structure
📦 resume-analyzer
│── 📁 src
│    ├── parser.py
│    ├── recommender.py
│    ├── scoring.py
│    └── utils.py
│── 📁 model
│── 📁 dataset
│── 📁 outputs
│── app.py
│── requirements.txt
│── README.md

⚙️ Installation & Setup
1️⃣ Clone the Repository
git clone <repo-url>
cd resume-analyzer

2️⃣ Install Dependencies
pip install -r requirements.txt

3️⃣ Download NLP Model
python -m spacy download en_core_web_sm

🔧 How It Works
Step	Process
1	User uploads resume
2	Resume text extraction (PDF parser)
3	NLP pipeline detects skills and keywords
4	ML engine compares profile with job dataset
5	System generates score + recommendations
📌 Sample Code Snippets
📄 Resume Text Extraction
import PyPDF2

def extract_text(file_path):
    with open(file_path, 'rb') as pdf:
        reader = PyPDF2.PdfReader(pdf)
        return " ".join([page.extract_text() for page in reader.pages])

🧠 Job Recommendation Engine
from sklearn.metrics.pairwise import cosine_similarity

def recommend(resume_vec, job_vectors, job_roles):
    scores = cosine_similarity([resume_vec], job_vectors)[0]
    ranked = sorted(zip(job_roles, scores), key=lambda x: x[1], reverse=True)
    return ranked[:5]

▶️ Execution

To run using Streamlit UI:

streamlit run app.py


OR backend mode:

python app.py

🧪 Testing Instructions

Use sample resumes in /dataset

Validate extracted skills

Compare recommendation accuracy

Test error handling (empty resume, invalid format)

🔮 Future Enhancements

Real-time job scraping (LinkedIn/Indeed API)

Support multilingual resumes

ATS compatibility scoring

Cloud deployment with authentication
