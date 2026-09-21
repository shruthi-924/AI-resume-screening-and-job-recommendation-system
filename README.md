# AI Resume Screening & Job Recommendation System

An intelligent web-based application designed to simplify the resume screening and job-search process. The system analyzes a candidate's resume, compares it with a given job description, calculates a compatibility score, highlights relevant and missing skills, and suggests suitable job roles.

The project combines **Python, Natural Language Processing (NLP), Machine Learning, and Flask** to build an automated resume analysis and recommendation platform.

---

## About the Project

Manually reviewing a large number of resumes can be time-consuming for recruiters and job seekers. This project aims to reduce that effort by automatically analyzing resume content and comparing it with job requirements.

Users can upload their resume and provide a job description to get useful insights such as:

* Resume-job compatibility score
* Skills that match the job requirements
* Skills that are missing
* Recommended job positions
* Relevant job details based on the candidate's profile

---

## Main Features

### Resume Analysis

* Supports **PDF and DOCX resumes**
* Extracts text automatically from uploaded files
* Cleans and preprocesses the extracted content
* Identifies important skills and keywords

### Job Matching

* Compares resume content with job requirements
* Converts text into numerical features using **TF-IDF**
* Calculates similarity using **Cosine Similarity**
* Produces a percentage-based compatibility score

### Skill Gap Identification

The application compares the skills found in the resume with the skills mentioned in the job description and displays:

* Commonly matched skills
* Skills that are required but not found in the resume

### Career Recommendations

Based on the skills extracted from the resume, the application searches the available job dataset and recommends relevant roles.

The recommendations provide information such as:

* Recommended job title
* Matching score
* Relevant skills
* Job description

---

## Match Score Classification

|         Score | Result        |
| ------------: | ------------- |
| 85% and above | Great Match   |
|     70% – 84% | Good Match    |
|     40% – 69% | Average Match |
|     Below 40% | Low Match     |

---

## Application Screenshots

### Dashboard

![Dashboard](screenshots/Home.png)

### Resume Submission

![Resume Upload](screenshots/ResumeUpload.png)

### Analysis Results

![Results](screenshots/Result.png)

---

## Technologies Used

| Category               | Technologies      |
| ---------------------- | ----------------- |
| Language               | Python            |
| Web Framework          | Flask             |
| NLP                    | NLTK              |
| Machine Learning       | Scikit-learn      |
| Text Representation    | TF-IDF            |
| Similarity Calculation | Cosine Similarity |
| Numerical Processing   | NumPy             |
| PDF Processing         | PyPDF2            |
| DOCX Processing        | python-docx       |
| Frontend               | HTML, CSS, Jinja2 |
| Dataset                | CSV               |

---

## System Workflow

```text
             User Input
                 |
        +--------+--------+
        |                 |
      Resume        Job Description
        |                 |
        v                 v
   Text Extraction    Text Processing
        |                 |
        +--------+--------+
                 |
                 v
          NLP Preprocessing
                 |
                 v
          Skill Identification
                 |
                 v
          TF-IDF Processing
                 |
                 v
        Cosine Similarity
                 |
                 v
          Match Score
                 |
        +--------+---------+
        |                  |
        v                  v
   Skill Analysis    Job Recommendation
        |                  |
        +--------+---------+
                 |
                 v
           Final Results
```

---

## Workflow Explanation

1. The user uploads a resume in PDF or DOCX format.
2. The application extracts the textual content from the resume.
3. The extracted content is cleaned using basic NLP preprocessing.
4. Important skills are identified from both the resume and job description.
5. TF-IDF is applied to represent the text numerically.
6. Cosine Similarity measures the similarity between the two documents.
7. A match percentage is generated based on the similarity score.
8. The system identifies matched and missing skills.
9. Resume skills are compared with the available job dataset.
10. Relevant job roles are displayed to the user.

---

## Directory Structure

```text
AI-Resume-Screening-System/
│
├── app.py
├── matcher.py
├── resume_parser.py
├── jobs.csv
├── req
```
