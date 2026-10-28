# AI Resume Parsing & Screening System

An AI-powered resume screening system built with Python, Groq API, and Pydantic to extract candidate information, analyze skills, and evaluate resumes against a job description.

## Overview

Recruiters often need to review multiple resumes to identify candidates whose qualifications match a specific job role. Manually comparing every resume can be time-consuming.

This project automates key parts of the screening process by extracting structured information from PDF and DOCX resumes, using an LLM to analyze candidate profiles, and generating a job-match score with supporting details.

## Features

- **Multi-format Resume Parsing:** Extracts text from PDF and DOCX files.
- **AI-Powered Information Extraction:** Identifies candidate details, skills, education, experience, projects, and certifications.
- **Job Description Analysis:** Converts job requirements into structured information.
- **Candidate Matching:** Compares candidate profiles with job requirements.
- **Skill Gap Analysis:** Identifies matching skills and missing important skills.
- **Experience Evaluation:** Checks whether the candidate meets the stated experience requirements.
- **Match Score and Verdict:** Generates an overall match score and a concise evaluation.
- **Candidate Ranking:** Sorts candidates by match score and displays the top two and lowest two candidates.

> **Note:** The current implementation uses a predefined job description for a Software Development Engineer role. You can customize it in `resume_parser.py`.

## Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| Groq API | LLM-powered resume analysis |
| Pydantic | Structured data validation and schemas |
| PyPDF | Extracting text from PDF resumes |
| python-docx | Extracting text from DOCX resumes |
| python
