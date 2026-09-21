# AI-Based Resume Screening & Job Recommendation System

An AI-powered web application that analyzes resumes against job descriptions, calculates a resume-job match score, identifies matched and missing skills, and recommends suitable job roles based on the skills detected in the resume.

The project combines **Natural Language Processing (NLP)**, **Machine Learning**, and **Flask web development** to demonstrate how an intelligent resume screening system can assist candidates and recruiters.

---

## Project Overview

Recruiters often spend significant time manually reviewing resumes and comparing candidate skills with job requirements.

This project demonstrates how **Artificial Intelligence and Natural Language Processing** can be used to automate part of this process.

The system allows a user to:

- Upload a resume in PDF or DOCX format
- Enter a job description
- Analyze the compatibility between the resume and the job description
- View a match percentage
- See matched and missing skills
- Receive job recommendations based on the skills detected in the resume

---

## Key Features

### Resume Screening

- Upload resumes in **PDF or DOCX format**
- Extract resume text automatically
- Preprocess text using NLP techniques
- Compare resume content with a job description

### Match Analysis

- Calculate resume-job similarity
- Use **TF-IDF vectorization**
- Use **Cosine Similarity**
- Generate an overall match percentage
- Categorize the result as:

| Match Score | Category |
|-------------|----------|
| ≥ 85% | Great Match |
| ≥ 70% | Good Match |
| ≥ 40% | Average Match |
| < 40% | Poor Match |

### Skill Analysis

The system identifies:

- Skills present in both the resume and job description
- Skills required by the job but missing from the resume

### Job Recommendations

The system analyzes the skills detected in the resume and recommends suitable roles from a predefined job dataset.

Each recommendation includes:

- Job title
- Match percentage
- Job description
- Matching skills

---

## Demo

### Home Page

![Home Page](screenshots/Home.png)

### Resume Upload

![Resume Upload](screenshots/ResumeUpload.png)

### Result & Job Recommendations

![Result](screenshots/Result.png)

---

## Tech Stack

### Programming Language

- Python

### Backend

- Flask

### Machine Learning & NLP

- NLTK
- Scikit-learn
- TF-IDF
- Cosine Similarity
- NumPy

### Document Processing

- PyPDF2
- python-docx

### Frontend

- HTML
- CSS
- Jinja2 Templates

### Data

- CSV-based job dataset

---

## How the System Works

```text

        Resume + Job Description
                   |
                   v
         Resume Text Extraction
                   |
                   v
           Text Preprocessing
                   |
                   v
            Skill Detection
                   |
                   v
           TF-IDF Vectorization
                   |
                   v
            Cosine Similarity
                   |
                   v
            Match Percentage
                   |
          +--------------------+
          |                    |
          v                    v
 Skill Gap Analysis    Job Recommendations
          |                    |
          +---------+----------+
                    |
                    v
              Web Interface
```

## Processing Pipeline

1. The user uploads a resume in PDF or DOCX format.
2. Resume text is extracted from the uploaded document.
3. NLP preprocessing is performed on the extracted text.
4. Skills are detected from the resume and job description.
5. Resume and job description text are converted into numerical representations using TF-IDF.
6. Cosine similarity is used to calculate text similarity.
7. The system generates an overall match score.
8. The candidate is categorized based on the match percentage.
9. Matched and missing skills are displayed.
10. The detected resume skills are used to recommend suitable job roles.

## Project Structure

```text
AI-Resume-Screening-System/
│
├── app.py
├── matcher.py
├── resume_parser.py
├── jobs.csv
├── requirements.txt
├── README.md
├── .gitignore
│
├── templates/
│   └── index.html
│
├── static/
│   └── style.css
│
├── screenshots/
│   ├── Home.png
│   ├── ResumeUpload.png
│   └── Result.png
│
└── sample_resumes/
    ├── SampleResume.pdf
    └── SampleJobDescription.docx
```
## How to Run Locally

### 1. Clone the repository
git clone https://github.com/Harshitha070705/AI-Resume-Screening-System.git
cd AI-Resume-Screening-System

### 2. Create and activate a virtual environment
python -m venv .venv
Windows PowerShell:
.venv\Scripts\Activate.ps1

### 3. Install dependencies
pip install -r requirements.txt

### 4. Run the application
python app.py

### 5. Open the application

Once the Flask server is running, open the following address in your browser:
```text
http://127.0.0.1:5000
```

### Limitations

- Matching is primarily based on textual similarity and predefined skill detection
- The system does not perform deep semantic understanding of candidate experience
- Skills that are implied but not explicitly mentioned may not be detected
- Results can vary depending on resume formatting and wording
- Job recommendations are generated from a predefined job dataset

### Future Improvements

- Advanced semantic matching using BERT or transformer-based models
- Resume ranking for multiple candidates
- More sophisticated skill extraction
- Database integration
- Authentication and user profiles
- Cloud deployment
- Larger and dynamically updated job datasets

### What I Learned

- Resume text extraction from PDF and DOCX files
- NLP preprocessing using NLTK
- Skill extraction and matching
- TF-IDF feature extraction
- Cosine similarity
- Flask backend development
- Frontend-backend integration
