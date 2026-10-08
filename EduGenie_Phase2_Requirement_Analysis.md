**PHASE 2**

# 2. Requirement Analysis Phase

## Functional Requirements
- Provide a web form with a task dropdown (Explain, QnA, Quiz, Summary, Recommend Path), a text area and a Submit button.
- Answer general knowledge and academic questions using Gemini 1.5 Pro.
- Explain complex concepts in simple language using the local LaMini-Flan-T5 model.
- Generate 3 multiple-choice questions with 4 options each from a topic or passage, returned as JSON.
- Summarize long educational passages into concise, easy-to-understand versions.
- Generate a personalized, structured learning path from beginner to advanced with resources.
- Display the result below the input box in real time.

## Non-Functional Requirements
- Lightweight and fast, running on CPU-based devices such as the Mac M1.
- Simple, clean and responsive interface built with HTML and CSS.
- Modular code with a separate module for every feature, so upgrades are easy.
- Scalable cloud-based backend for AI intelligence.
- Gemini API key stored securely and never shared in the code.
- Graceful error handling with clear, detailed error messages.

## Inputs and Outputs

| Feature | Input | Output |
|---|---|---|
| Q&A | A question | Smart, concise answer |
| Explanation | A concept or topic | Simple, readable explanation |
| Quiz | Topic or passage | 3 MCQs, 4 options each, correct answer feedback |
| Summary | Long paragraph | Short, clear summary |
| Learning path | A topic (e.g. SQL) | Beginner-to-advanced plan with resources |

## Pre-requisites

| Requirement | Details |
|---|---|
| Python 3.10+ | Install from the official site, tick “Add Python to PATH”, verify with *python --version* |
| FastAPI | Backend framework (official docs and tutorials available) |
| Uvicorn | ASGI server; installed with pip install uvicorn |
| Jinja2 | HTML templating engine; installed with pip install jinja2 |
| HTML & CSS | Basic templating used in the templates and static folders |
| Gemini API Key | Sign in to Google AI Studio, create a project, enable the Gemini API, generate and securely store the key |

## Assumptions and Constraints
- Cloud features need a valid Gemini API key and an internet connection.
- AI-generated answers depend on model output and may vary between runs.
- This version is run locally; it has no user accounts or progress tracking.
