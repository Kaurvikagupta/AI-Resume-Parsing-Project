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
| python-dotenv | Managing environment variables |
| uv | Python project and dependency management |

## Project Structure

```text
AI_Project/
├── resumes/
│   └── .gitkeep
├── src/
│   └── ai_project/
│       └── __init__.py
├── .env.example
├── .gitignore
├── .python-version
├── main.py
├── resume_parser.py
├── pyproject.toml
├── README.md
└── uv.lock
```

The `resumes/` directory is used for input resumes. Add your authorized sample PDF or DOCX files locally before running the program.

## Getting Started

### Prerequisites

Make sure you have installed:

- Python
- [uv](https://docs.astral.sh/uv/)
- A Groq API key from the [Groq Console](https://console.groq.com/keys)

### 1. Clone the Repository

```bash
git clone https://github.com/Kaurvikagupta/AI-Resume-Parsing-Project.git
cd AI-Resume-Parsing-Project
```

### 2. Install Dependencies

```bash
uv sync
```

This installs the project's dependencies and prepares the virtual environment.

### 3. Configure the API Key

Create a `.env` file in the project root.

On Windows PowerShell:

```powershell
Copy-Item .env.example .env
```

Open `.env` and add your own Groq API key:

```dotenv
GROQ_API_KEY=your_groq_api_key_here
```

Replace the placeholder with your actual API key.

**Never commit your `.env` file or expose your API key in source code, screenshots, or public repositories.**

### 4. Add Resume Files

Place your authorized sample resumes inside the `resumes/` directory.

Supported formats:

- `.pdf`
- `.docx`

The program processes these files from the `resumes/` folder.

### 5. Run the Application

```bash
uv run resume_parser.py
```

The program reads the resumes, extracts candidate information, evaluates each profile against the predefined job description, and prints the screening results in the terminal.

## Sample Output

The output follows this general structure:

```text
Processing: candidate_resume.pdf

Score: <match score>

TOP 2 CANDIDATES
Candidate Name - <score> %

{
  "matching_skills": [],
  "missing_important_skills": [],
  "experience_requirement_met": true,
  "overall_match_percentage": 0,
  "final_verdict": "..."
}

LOWEST 2 CANDIDATES
Candidate Name - <score> %
```

Actual scores and evaluation details depend on the resume contents, job requirements, and model response.

## How It Works

1. **Job Description Processing:** The LLM extracts structured job requirements, skills, responsibilities, and qualifications.
2. **Resume Text Extraction:** The system reads text from PDF and DOCX files.
3. **Information Parsing:** The LLM converts resume content into structured candidate information.
4. **Candidate Evaluation:** Each parsed resume is compared against the job requirements.
5. **Scoring and Ranking:** The system calculates a model-generated match score and sorts candidates.
6. **Result Generation:** The terminal displays the top two and lowest two matches, along with evaluation details.

## Customization

To evaluate candidates for a different role, update the `job_description` variable near the beginning of `resume_parser.py`.

Include the relevant job responsibilities, required skills, qualifications, and experience expectations.

## Important Notes

- The match score is an AI-generated estimate, not a scientifically validated probability of job success.
- AI-generated evaluations can contain errors or inconsistencies. Human review is necessary before making recruitment decisions.
- Resume files may contain sensitive personal information. Use authorized test data and avoid uploading real candidate resumes to a public repository.
- Keep API credentials in `.env` and ensure `.env` is excluded through `.gitignore`.
- API availability, rate limits, and usage costs depend on the provider and your account.

## Future Enhancements

- Web-based dashboard for uploading resumes.
- User-defined job descriptions through an interface.
- Downloadable screening reports in CSV or PDF format.
- Candidate filtering by skills, education, and experience.
- Persistent storage for candidate profiles and screening history.
- Improved evaluation consistency and recruiter feedback.

## Author

**Kaurvika Gupta**

GitHub: [@Kaurvikagupta](https://github.com/Kaurvikagupta)

---

If you find this project useful, consider giving the repository a ⭐ on GitHub.

